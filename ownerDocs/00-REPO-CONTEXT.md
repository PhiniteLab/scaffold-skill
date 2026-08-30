# Repository context

**One page that orients an agent before it reads anything else in this repository.**
Read after `README.md` — the workspace area map — before touching code or manuscripts.

> Owner-owned and repository-specific. The template ships this file EMPTY; the scaffold
> creates it once and never overwrites it, and `--sync` never touches it. Fill it in your
> own words — the headings below are a prompt, not a schema.

---

## What this repository is

This repository ships the **`popperian-coding`** Claude Agent Skill (`SKILL.md`'s `name:`
field) — a falsification-over-verification coding scaffold covering four coding modes
(`review`, `generation`, `verification`, `test_construction`) and enforcing six invariants:
an explicit conjecture inventory, mandatory severity scores, oracle independence, an
MDL-based ad-hoc-rescue blocker, abstention as a first-class outcome, and a versioned run
trace (`README.md`, `SKILL.md`). Its scope is wider than a bare manuscript repo: besides
`SKILL.md` it holds the four mode protocols under `modes/`, three helper scripts under
`scripts/` (`severity.py`, `mdl.py`, `trace.py`), and `catalogs/` (a mutation-operator
catalogue and per-domain bug-class/implicit-requirement checklists, currently only a
`web_backend` domain). Its `PAPER.yml` role is `studied-artifact` (`paper_of_record: false`)
— it is the **object of study** in a companion controlled evaluation, not the evaluation
harness or the manuscript home; no LaTeX source for arXiv:2606.06454 exists anywhere on disk
in this collection (`latex_home: null`, `PAPER.yml` notes). It is deliberately **not**
renamed to match the repository name `scaffold-skill`: the skill keeps its registered
identity `popperian-coding` because a byte-identical copy is vendored into the companion
evaluation repository `exec-refute` (`PAPER.yml` `companions[0]`, `README.md`).

## Scientific claim under development

The companion paper studying this skill reports a **calibrated negative result**: under
HumanEval+ execution-oracle evaluation (Claude Sonnet 4.6 via the Claude Code agentic
serving path, and Qwen2.5-Coder-0.5B local Ollama), the full skill showed no separable
execution-correctness benefit over a labels-only scaffold of the same structure — measured
best-of-eight gains tracked scaffold *structure* rather than the incremental Popperian
procedural content, and a same-model self-judge did not beat random selection among its own
samples (`README.md` "Companion paper"). This repository does not itself carry a numeric
success criterion to meet — the evaluation, its metrics, and the pre-registered protocol
(placebo + labels-only + execution oracle + halo sentinel) live in the companion repository
`exec-refute`, not here.

## Where the truth lives

- code that runs the experiments -> Not in this repository: this repo is the skill under
  test (`SKILL.md`, `modes/`, `scripts/`, `catalogs/`); the controlled-evaluation harness
  lives in the companion repository `exec-refute` (`PAPER.yml` notes, `README.md`
  companion-paper section).
- the current method specification -> `SKILL.md` (six invariants, output-label discipline,
  mode router) plus the four `modes/*.md` protocol files. `ownerDocs/myMethods/` holds only
  the scaffold `README.md` and an empty `evidence/` directory — no numbered method file has
  been registered there.
- results an outside reader can trust -> Not in this repository; no `experiments/` or
  results directory exists here. The paper's reported evaluation results live in
  `exec-refute`.
- the corpus -> `ownerDocs/myLiterature/MANIFEST.yaml`

## Toolchain and how to run it

Not a Python package or app — this is a Claude Agent Skill directory. Install by placing it
under the skill's own registered identity, not this repository's name:
`~/.claude/skills/popperian-coding/`, so `SKILL.md` sits together with `modes/`, `scripts/`,
`catalogs/` (`README.md` "Using it with Claude"). `Makefile` documents the collection's
interoperability verbs honestly as no-ops where nothing applies (`setup`, `test`, `paper`,
`falsify`, `repro` all print why there is nothing to run, per `Makefile`'s own header
comment) except:

```bash
make lint    # ruff check .
make type    # pyright scripts
make smoke   # python3 -m compileall -q scripts; each of severity.py/mdl.py/trace.py --help
```

`make -n smoke` (dry run, confirmed in this pass) resolves to exactly those four commands.
**How long `make smoke` takes is not stated in this repository.**

## Constraints and non-goals

- The skill's registered identity (`SKILL.md`'s `name: popperian-coding`) must never be
  renamed to match the repository name `scaffold-skill` — doing so would desynchronize it
  from the byte-identical copy vendored in `exec-refute` and from the name the companion
  paper studies (`PAPER.yml` notes).
- No LaTeX source for arXiv:2606.06454 exists in this repository or collection as of the
  `PAPER.yml` notes' timestamp; only a compiled PDF with no accompanying source lives at
  `exec-refute/makale1.pdf`. This repository does not attempt to reconstruct one.
- This repository does not itself run or host the controlled evaluation, its metrics, or its
  results — that is explicitly out of scope here and lives in `exec-refute` (`Makefile`
  `falsify`/`repro`/`test` targets, `PAPER.yml` notes).
- License is MIT (`README.md`, `LICENSE`).

## Current blockers

None recorded. `tasks/todo.md` is empty, and no open blocker is stated in `README.md`,
`CHANGELOG.md`, or `PAPER.yml`.
