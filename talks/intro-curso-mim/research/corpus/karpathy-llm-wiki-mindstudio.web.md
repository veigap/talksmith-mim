---
source_file: karpathy-llm-wiki-mindstudio
source_type: web-capture
ingested_at: 2026-07-15
---

# What Is Andrej Karpathy's LLM Wiki? How to Build a Personal Knowledge Base With Claude Code | MindStudio

## Provenance
- Original location: research/web/karpathy-llm-wiki-mindstudio/ (page.md used as text input; original.html available, not needed — no fallback triggered)
- Format: web capture (html + extracted markdown)
- Author / source (if known): MindStudio Team
- Date of original (if known): April 6, 2026 (published); "Last updated: 2026-05-11 — added related Claude Code workflow links and second-brain comparisons"
- URL: https://www.mindstudio.ai/blog/andrej-karpathy-llm-wiki-knowledge-base-claude-code
- Fetched at: 2026-07-16T00:34:41Z (per metadata.yaml)
- HTTP status: 200 · byte_size: 100607

## Key claims
- Andrej Karpathy (co-founder of OpenAI, former Tesla AI director) has publicly described an "LLM wiki" pattern: personal notes/documents kept as plain markdown files, queried by an LLM (e.g., Claude Code) that reasons over them — rather than organized for human browsing.
- Core distinction: traditional notes apps are built for human navigation (you remember where things are); an LLM wiki is optimized for the model to read on your behalf (you describe what you need, Claude finds and synthesizes across the whole base).
- Markdown is the recommended format because: it's portable/future-proof (plain text, opens anywhere, no vendor lock-in); LLMs are trained on huge volumes of markdown (READMEs, docs, forums) so they parse its structure (headers, bullets, code blocks, bold) as signal, not noise; it forces clarity (headers/lists demand organization); no lock-in (works with git, VS Code, Obsidian, terminal).
- Minimal architecture, three components: (1) a folder of markdown files, (2) a consistent internal structure per file (title, brief summary, tagged topics, then content), (3) Claude Code as the query interface (reads/searches/creates/updates files, executes shell commands).
- No database, no vector embeddings required for the base case (can add later); "just files and a capable model."
- Claude Code = Anthropic's terminal-based coding agent; unlike browser-based Claude, it has direct local filesystem access.
- Recommended front-end: Obsidian (local-first markdown editor, plugin ecosystem, `[[wiki links]]`), though not required — any text editor works (VS Code, Typora, iA Writer, Zed, Vim).
- Setup workflow (5-minute claim): install Obsidian → create vault → define a note template (title, Summary, Tags, Created/Last Updated, Content, Related Notes) → organize into broad top-level folders (`_templates/`, `projects/`, `research/`, `reference/`, `meetings/`, `inbox/`) → write first notes → install Claude Code (`npm install -g @anthropic-ai/claude-code`, needs Node.js) → query via `cd ~/wiki && claude`.
- Best practices: write one-line summaries (Claude reads these to decide relevance before reading full files); use consistent terminology (or alias lines) across notes; link notes to each other (`[[wiki links]]` give Claude a richer graph to traverse than flat files); keep notes focused (ten 1,000-word notes beat one 10,000-word catch-all); use an `/inbox` pattern for rough capture, then ask Claude to triage/file it later.
- Scaling: direct file-reading works well up to "a few hundred notes"; beyond that, add a semantic-search/RAG layer (e.g., LlamaIndex vector index) or package wiki-querying as a reusable Claude Code Skill to pre-filter/summarize/route queries and cut token cost.
- Claude 3.5 Sonnet context window ≈200,000 tokens — comfortably reads tens of thousands of words per session; most personal wikis (up to a few hundred focused notes) don't need RAG.
- MindStudio's own pitch: wrapping the same markdown-wiki pattern in a MindStudio agent lets a team query it through a web UI without touching Claude Code/terminal; MindStudio offers access to Claude/GPT/Gemini/200+ models and 1,000+ integrations (Slack, email, project tools).

## Definitions and terminology
- **LLM wiki**: a personal knowledge management pattern — plain markdown files organized with consistent structure, designed to be queried by an LLM/coding agent rather than browsed manually. Term/pattern attributed to Andrej Karpathy.
- **Vault** (Obsidian term): just a folder — everything in it is plain markdown.
- **Claude Code**: Anthropic's terminal-based coding agent with direct local filesystem access; used here as the "query interface" for the wiki, not primarily as a coding tool.
- **RAG (Retrieval Augmented Generation)**: an "advanced" addition — a vector index over markdown files that narrows candidates before Claude reads full files; framed as unnecessary for most personal wikis, useful only past "a few hundred notes."
- **Skill (Claude Code)**: a reusable packaged capability that can pre-filter notes, summarize subsections, and route queries to cut token cost as a wiki scales.

## Evidence and examples
- No survey/dataset — this is an explainer/how-to article, not primary research. Its "evidence" is procedural (step-by-step setup) and illustrative example queries: "What notes do I have about machine learning interpretability?", "Summarize everything in my research folder related to RAG systems.", "I'm writing a proposal on X — what relevant notes do I have?", "Find any notes where I mentioned the vendor Acme Corp and summarize the key points."
- Cites a related MindStudio article claiming Karpathy's LLM wiki pattern is "reportedly 70x more efficient than RAG" (see the "Related Articles" teaser for a *different* MindStudio post — "What Is the Karpathy LLM Wiki Pattern?" dated April 11, 2026 — this 70x figure is NOT substantiated within the body of the article actually captured here; it appears only in a teaser/promo blurb for a sibling article. Flag before citing.)

## Inconsistencies / open questions
- This article is explicitly MindStudio content-marketing — it pivots at the end ("Where MindStudio Fits This Workflow") to pitch MindStudio's own no-code agent platform as the "team-facing" extension of Karpathy's pattern. The Karpathy attribution itself is undocumented in-article (no direct quote, talk, or tweet from Karpathy is linked or cited — the piece paraphrases "he calls it" without a source link). Treat the core pattern description as reliable secondary reporting, but the specific attribution/quotes should not be treated as verified primary-source claims from Karpathy himself.
- The "70x more efficient than RAG" claim (surfaced in a teaser for a sibling MindStudio article, not in this article's body) is unverified and not sourced within the captured text — do not cite as fact without checking the actual sibling article.
- No fallback to original.html was needed — page.md is well-formed (22,505 bytes, 44 headings), well above the fallback threshold.
- Heavy inline promotional content (Remy/Hermes workshop ads, MindStudio product plugs) interleaved throughout the body — preserved in the extraction but should be filtered out as noise when drafting slides; not treated as "key claims."

## Images / diagrams
- `karpathy-llm-wiki-mindstudio.web/images/1081916b-7b01-435a-8c1f-c853fc4c894b.png`
  - Provenance: article hero/header image.
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/MindStudio-lockup-blk.svg`
  - Provenance: MindStudio site logo/lockup (nav header).
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/lockup-h-md.svg`
  - Provenance: "Remy" product logo/lockup, from the "Remy is new. The platform isn't." promo block.
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/2f72d608-9e6a-4ec2-b2f1-5063df20ef36.png`
  - Provenance: promo banner — "Catch up on Hermes — free 60-minute live workshop."
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/76b81a63-51ec-43f4-b4ea-0b5023be600a_1780006013492.png`
  - Provenance: small "Hermes" icon, reused across multiple promo blocks in the article body.
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/8edf5cbc-5b63-4999-9079-6aeca2aafd65.png`
  - Provenance: promo banner — "Hermes, walked through line by line — free 1-hour workshop."
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/922211b2-4085-4d29-85af-55d6920d46d0.png`
  - Provenance: promo banner — "A free 1-hour Hermes workshop."
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/c8d61682-41d9-44c0-a2fe-5299b2d46f88.png`
  - Provenance: promo banner — "Wondering what the Hermes hype is about? Free 60-minute primer."
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/5de43b2b-287a-4ebf-b285-894e06dbb107.png`
  - Provenance: "Related Articles" thumbnail for the sibling post "What Is the Karpathy LLM Wiki Pattern? How to Build a Personal Knowledge Base With Claude" (April 11, 2026) — the article claiming the unverified "70x more efficient than RAG" figure.
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/a44b122a-1fac-4a4d-888a-16d58ece8afd.png`
  - Provenance: "Related Articles" thumbnail for "Claude Code Source Code Leak: 8 Hidden Features You Can Use Right Now."
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/25a8de47-59a9-4a2b-8240-1c925644dd5d.png`
  - Provenance: "Related Articles" thumbnail for "What Is Claude Co-work Projects? How to Organize AI Agent Tasks by Context."
  - <!-- pending: process_images -->
- `karpathy-llm-wiki-mindstudio.web/images/978def76-49ce-4733-ab9e-fb4eb6215ba2.png`
  - Provenance: "Related Articles" thumbnail for "What Is GStack? Gary Tan's Open-Source Startup Framework for Claude Code."
  - <!-- pending: process_images -->

## Raw / preserved excerpts
> He calls it an LLM wiki. The concept is straightforward. Instead of scattering knowledge across Notion, Google Docs, browser bookmarks, and sticky notes, you keep everything as structured markdown files. Then you point Claude Code (or any capable coding agent) at that folder and ask it questions.

> An LLM wiki is optimized for the model to read on your behalf. That shift changes everything about how you structure information.

> The model doesn't care about your folder hierarchy or tags. It reads text. So plain markdown — which is just text with minimal syntax — is the ideal format.

> That's it. No database. No vector embeddings (though you can add them later). No server. Just files and a capable model.

> The best knowledge management system is one you'll actually use. A folder of markdown files is about as low-friction as it gets—and pointing Claude at it takes five minutes. Start small, keep notes focused, and let the system grow with you.

Note template given in-article (`_templates/note.md`):
```
# undefined

**Summary**: One sentence describing this note.
**Tags**: #topic1 #topic2
**Created**: 2026-04-06T00:00:00+00:00
**Last Updated**: 2026-04-06T00:00:00+00:00

---

## Content

Write the main content here.

## Related Notes

- [[Note Title]]
```

Recommended folder layout:
```
wiki/
├── _templates/
├── projects/
├── research/
├── reference/
├── meetings/
└── inbox/
```
