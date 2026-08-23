# REPO-INFO — what exists technically, and how to enter it

This layer answers **what the repository IS**. `ownerDocs/` answers **why it exists**.
A fact belongs in exactly one of them; when they disagree, `ownerDocs/` is right about
intent and this layer is right about what the code currently is.

## Purpose

Orient a reader — human or agent — who has never opened this repository, using only
facts the tree demonstrably contains.

## Scope and Boundaries

In scope: the components below and the generated inventory in `CODE-MAP.md`.
Out of scope: rationale, decisions and claims — those are `ownerDocs/`, `ARCHITECTURE.md`
and `TRACEABILITY.md`, none of which any tool may write.

## Top-level components

Derived from the tree. A description is this component's own `README.md` heading; where
it has none the row says so rather than guessing.

| Component | Contents | Description |
|---|---|---|
| `modes/` | 4 Markdown | _not described — no README.md heading here_ |
| `ownerDocs/` | 18 Markdown | Owner Documentation Workspace |
| `scripts/` | 4 Python | _not described — no README.md heading here_ |
| `tasks/` | 1 Markdown | _not described — no README.md heading here_ |
| _(repository root)_ | 3 Markdown | files at the top level |

## Registered components

**Empty on purpose.** Registering a component here obliges someone to write that
component's README to the section contract, and `repo_info.py check` reports a
registered path whose README is absent or incomplete. Register a component in the
table below at the moment you write its README, never before.

| ID | Path |
|---|---|

## Maintenance and Related Documentation

`CODE-MAP.md` is GENERATED — run `python3 ~/.claude/bin/repo_info.py sync`, never edit
it by hand. This file and the curated documents beside it are written by hand and must
be updated in the SAME turn as a structural change. Run `python3
~/.claude/bin/repo_info.py check` to see what this layer currently reports.
