# Talksmith Plugin Bug Triage

Collected from the `talks/claude-cowork` production run on 2026-07-17. This file is repo-local triage for later fixes in the Talksmith plugin.

## Actionable Bugs

### P1 - `prepare-render-args` writes session/mount paths into subagent args

- **Where:** `skills/polish-ascii/polish_ascii.py`, subcommand `prepare-render-args`.
- **Observed:** Args files contained paths rooted in the session/VM mount (`/sessions/<slug>/mnt/...`). Some worker contexts tried to read/write through host paths instead, so the first read failed unless the caller manually explained the VM-to-host mapping.
- **Current script state:** `--repo-root` is only copied into the payload. It does not re-anchor `ascii_file` or `output_path`, which are still derived from the absolute `final_path` captured by `scan`.
- **Expected:** `--repo-root` should control the paths emitted in args, or the plan should store paths relative to the Talk root and materialize them per execution context.
- **Candidate fix:** Store `final_path`, `ascii_file`, and `output_path` relative to repo/Talk root in the plan, then resolve them at `prepare-render-args` time using `--repo-root`. If absolute plan paths remain, add an explicit `--path-map from=to` or a loud warning when `repo_root` and `final_path` disagree.

### P1 - Feedback stripping can corrupt slide boundaries if blank-line guard is absent

- **Where:** Editor Step 6 strip of `Presenter feedback` fields; exact implementation may live in orchestration/editor logic rather than a standalone script.
- **Observed:** A manual strip once left `texto\n---` with no blank line before a slide boundary. Markdown parsed the boundary as a setext H2 underline and silently corrupted many slide separators.
- **Current mitigation:** The Cowork run added an explicit guard in practice: abort if the line before a feedback header/boundary is non-blank. That guard should live in plugin code/tests, not in operator memory.
- **Expected:** Removing `Presenter feedback` must preserve slide boundaries as thematic breaks.
- **Candidate fix:** Add a deterministic stripper helper with a test fixture containing `paragraph\n\n### Presenter feedback\n...\n---`. Assert the output has `paragraph\n\n---`, never `paragraph\n---`.

### P2 - Stale generated diagram/image triplets accumulate after major renumbering

- **Where:** Step 6 Polish, `talks/<Talk>/images/` generated assets.
- **Observed:** After re-architecture/renumbering, old `.svg` / `.png` / `.ascii` triplets remain in `images/`; final output references the new slugs, but the folder carries obsolete generated assets. This confused later audits and required manual deletion.
- **Expected:** Polish should distinguish presenter-owned source images from generated diagram/asides and offer a safe cleanup plan.
- **Candidate fix:** Add a non-destructive `polish-ascii gc --final talks/<Talk>/final.md --images talks/<Talk>/images --dry-run` that lists generated triplets not referenced by `final.md`. Only delete on explicit `--apply`. Detect generated assets by `.ascii` sidecar or SVG stamp, never by `.png` alone.

### P2 - HTML renderer silently drops fields for certain template choices

- **Where:** `skills/md-to-deck/html_style.py` templates and the slide-model fill contract.
- **Observed examples:**
  - `content-image` renders only `images[0]`, so slides with two screenshots need `figures` even when the catalog says `figures` expects three or more.
  - `content+cards+image` ignored `lead` in at least one run.
  - `divider` / `statement` ignore body images, so the “Demo time” banner PNG existed but did not appear in `html-strict`.
- **Expected:** A template should either render every schema field it accepts, or the preflight should fail before rendering with a clear “field will be ignored” message.
- **Candidate fix:** Add a model-to-template coverage audit for HTML, parallel to `block_coverage`, that detects non-empty fields not consumed by the selected template. Also clarify slide-template docs: exact image counts and which templates render `lead`, `facts`, `images`, `highlights`, and `notes`.

### P2 - Icon suggestions can become broken refs if the name is wrong

- **Where:** `skills/md-to-deck/html_style.py` / `icon_fetch.py` and fill guidance.
- **Observed:** Suggested icon names are used verbatim; a typo can produce a missing icon unless the renderer falls back. In the Cowork run, the safer path was to omit item-level icons and let the renderer content-match against the live catalog.
- **Expected:** Invalid suggested icons should fall back to content-match or a known safe icon, with a warning in the render report.
- **Candidate fix:** Validate every explicit icon name against the cached catalog. If absent, record `invalid_icon: <name>` and replace with `icon_for(label, body)`.

### P2 - Live view and final render can reuse stale slide-models too easily

- **Where:** Step 5.5 / Step 7 `md-to-deck` workflow.
- **Observed:** `output/slide-model.draft.json`, `output/slide-model.json`, and `output/html/index.html` can represent different source states (`draft.md`, `final.md`, pre-Polish art, post-Polish art). The Cowork run needed manual reasoning about when reuse was safe.
- **Expected:** Render outputs should carry source fingerprints and refuse unsafe reuse.
- **Candidate fix:** Stamp slide-model and HTML outputs with hashes of `draft.md`/`final.md` plus referenced image hashes. Add `model_freshness.py` checks to Step 5.5 and Step 7 by default.

### P2 - Render FILL needs source-image coverage preflight

- **Where:** Step 7 `md-to-deck` FILL / model validation.
- **Observed:** During a from-scratch `html-strict` render of the Cowork talk, the first fresh model omitted `images/screenshot-cowork-tab.png` from the "(Demo time)" slide because that slide mixes a documentation-only ASCII banner with a screenshot. The model was otherwise valid and would have rendered without the screenshot unless manually compared against `final.md`.
- **Expected:** Every load-bearing Markdown image ref in `final.md` should either appear in the model or be explicitly recorded as intentionally omitted.
- **Candidate fix:** Add a deterministic pre-render audit that compares image refs in `final.md` to image refs in `slide-model.json`, ignoring only refs inside `ascii-source` comments and explicit omission annotations. Fail or warn with the missing list before rendering.

### P3 - XML comments with decorative `--` sequences are invalid

- **Where:** `talksmith:ascii-to-svg` output generation and validation.
- **Observed:** Decorative comments like `<!-- ---- -->` are invalid XML because `--` is forbidden inside XML comments. `validate_svg.py` caught this in one render before critique.
- **Expected:** The generation rules should forbid decorative XML comments; validation should keep catching them.
- **Candidate fix:** Add this to `config/diagram-style.md` and/or `ascii-to-svg/SKILL.md`; add a unit test in `tests/skills/ascii-to-svg` that `validate_svg.py` rejects comments containing `--`.

### P3 - Rasterized PNGs can contain missing-glyph boxes from Unicode labels

- **Where:** `talksmith:ascii-to-svg` visual generation and raster QA.
- **Observed:** In the Cowork polish rerun, `s4-2-1-excel-a-agentes.svg` used Unicode arrow glyphs (`→ developers`, `→ knowledge workers`). The SVG was valid, but the rasterized PNG showed square missing-glyph boxes in the deck asset. Manual visual QA caught it; replacing the glyphs with plain text labels fixed the PNG.
- **Expected:** Generated SVGs should avoid fragile Unicode symbols in labels unless the renderer/font stack is known to support them, and raster QA should make missing glyphs easier to catch.
- **Candidate fix:** Add a diagram-style rule: prefer drawn arrows/lines or ASCII-safe text labels over inline Unicode arrows/checks/crosses in text nodes. Add an optional raster audit that flags repeated square-glyph shapes or known tofu glyph bytes after PNG generation.

## Diagram Rendering Rules To Promote

These are not script crashes, but they recurred as visual defects and belong in `config/diagram-style.md` or `ascii-to-svg/SKILL.md`.

- **Arrow markers:** declare `markerUnits="userSpaceOnUse"` instead of relying on the SVG default `strokeWidth`; otherwise thicker arrows scale the arrowhead and can hit the destination box.
- **Arrow termination:** the shaft should end on the destination edge; `refX` / marker geometry should handle inset. Ending the shaft before the edge creates visible gaps.
- **Inline `<tspan>` under centered text:** avoid mixed inline tspans inside `<text text-anchor="middle">`; cairosvg can overprint runs instead of advancing x. Use separate positioned `<text>` nodes or make the whole text element bold/monospace.
- **Preserve leading whitespace:** code-like labels or YAML continuations need `xml:space="preserve"`; otherwise indentation collapses.
- **Unicode symbol text:** avoid Unicode arrows/checkmarks/crosses inside text labels unless visually verified after rasterization; prefer drawn arrows or plain words.

## Workflow / Spec Inconsistencies

### Documentation-only ASCII is too blunt for “banner + screenshot” slides

- **Where:** `agents/diagram-illustrator.md` and `skills/polish-ascii`.
- **Observed:** Any slide with a Markdown image ref makes all ASCII blocks documentation-only. This is correct for “small explanatory ASCII beside a screenshot,” but wrong for a banner/interstitial plus screenshot fallback. The Cowork slide 4.5 still has this open decision.
- **Expected:** The editor should be able to mark an ASCII block as render-driving even when the slide also contains a screenshot, or mark it as documentation-only explicitly.
- **Candidate fix:** Add explicit block hints, e.g. `<!-- ascii-render: force -->` and `<!-- ascii-render: documentation-only -->`, with scan defaulting to current behavior. The scan report should call out conflicts.

### Step numbering in old memory says “Step 8” for strict render

- **Where:** Historical `memory.md`.
- **Observed:** Older entries call strict render “Step 8” while current orchestrator uses Step 7 for Render and Step 8 for Learnings.
- **Expected:** Current spec is correct; historical notes are confusing when mined for bugs.
- **Candidate fix:** No code change required unless a migration tool exists. In future memory entries, render should always be Step 7.

## Closed / Do Not Chase Unless Reproduced

- **`polish_ascii.py cleanup` not escaping `-->` in `ascii-source`: closed.** Current installed plugin escaped `-->` to `--&gt;` automatically; manual patching would double-escape.
- **Idempotency by slug/prefix: closed in current 0.67.0.** `polish_ascii.py` now stamps `talksmith-ascii-sha256` and `prepare-render-args` reuses only when the digest matches. Filename alone is not consulted.
- **`validate_svg.py` inaccessible / plugin not mounted: closed in current environment.** The plugin is mounted under `.remote-plugins`; `validate_svg.py`, `rasterize.py`, and `audit_aspect.py` run there.
- **`qlmanage` fallback: closed in current 0.67.0.** `ascii-to-svg/SKILL.md` now says `rasterize.py` uses cairosvg only, with no qlmanage fallback.
- **`diagram-style.md` looked up under repo config: closed in current 0.67.0 docs.** `ascii-to-svg/SKILL.md` now explicitly loads `${CLAUDE_PLUGIN_ROOT}/config/diagram-style.md`.
- **Cut material ASCII scan bug: not reproduced.** Current `polish-ascii scan` reports `skipped_non_slide` for ASCII under `# Cut material`, so it does not require retagging to `text` unless a new fixture proves otherwise.
