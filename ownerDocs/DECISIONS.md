# Decisions

This append-only file records choices that would otherwise be re-litigated. A decision is
not a result or a method specification. Results belong in `myProgression/`; method content
belongs in `myMethods/`.

## Entry format

Replace `D-XXX` with the next unused stable ID, then copy the block below for each new
decision. Never renumber or rewrite a settled entry. A later decision declares which
earlier IDs it supersedes; the earlier entry remains unchanged.

```text
## D-XXX — <Decision Title>

- **Date:** <!-- YYYY-MM-DD -->
- **Decision:** <!-- actionable choice -->
- **Rationale:** <!-- reason that drove the choice -->
- **Rejected alternatives:** <!-- alternatives and their costs or failure modes -->
- **Affected areas:** <!-- repository-relative paths, claims, methods, or work units -->
- **Reversibility:** <!-- reversible | costly to reverse | one-way door -->
- **Evidence:** <!-- measured evidence or "decided without measurement" -->
- **Revisit if:** <!-- observation that should reopen the decision -->
- **Supersedes:** none
```
