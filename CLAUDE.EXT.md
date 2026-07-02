# Talksmith — subject repo extensions

Local extensions to [`CLAUDE.md`](CLAUDE.md) for this subject repo. `CLAUDE.md` is the Talksmith stub (overwritten on every `/talksmith:init`), so subject-specific conventions live here instead, where they survive re-inits. Treat the rules below as additive to the orchestrator spec.

## Repo-specific conventions

### `missions/` — class assignments

The `missions/` directory holds all the missions: the assignments for each one of the classes. Each mission corresponds to a class and defines the work assigned for it. Consult this directory to understand what each class requires, and keep it as the source of truth for per-class assignments.

### `README.md` — the agenda

`README.md` is the agenda for the subject. It must be kept up to date: whenever the schedule, class order, topics, or dates change, update `README.md` in the same pass so it always reflects the current plan.
