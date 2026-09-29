# Intent

[← Back to README](../../README.md) · Next: [Spec](spec.md) → [Plan](plan.md)

> This is the first of three linked documents: **Intent → Spec → Plan**. They were written *after the fact*, based only on what exists in the repository. Their purpose is to state the project's intent, and the intent of this reorganization, clearly enough for any human or automated contributor to work from.

## 1. Original Project Intent (Reconstructed)

| Item | Statement | Status |
|---|---|---|
| Purpose | A desktop GUI for applying filters to photographs | Inferred (repository name `Photo-filters`, file name `filtros`) |
| Platform | MATLAB, with the GUI built in GUIDE v2.5 | Confirmed |
| Interaction model | The user picks a filter from a list and uses buttons to trigger actions | Inferred (`listbox2`, `p1`, `pushbutton2`) |
| Target users | — | Unknown |
| Origin (academic / personal / other) | — | Unknown |
| Level of completion | Scaffold only: no filter logic, no layout file | Confirmed |

**Problem the project set out to solve (inferred):** give a user a simple, point-and-click way to transform an image with a chosen filter, without writing MATLAB code.

## 2. Repository Modernization Intent

**Modernize the repository, not the project.**

### Goals

1. Preserve the original implementation exactly, byte for byte.
2. Make the repository easy to understand without opening the source code.
3. Record what is **confirmed**, what is **inferred** and what is **unknown**, and never present an inference as a fact.
4. Present the repository as an honest historical entry in a technical portfolio.
5. Give future automated contributors clear intent, specification and guardrails ([`AGENTS.md`](../../AGENTS.md)).

### Non-Goals

- Implementing the missing filters or callbacks.
- Recreating or guessing the missing `filtros.fig` layout.
- Migrating from GUIDE to App Designer.
- Adding build systems, CI/CD, tests, containers, linters or package managers.
- Making the project look larger or more finished than it is.

## 3. Constraints

- `src/filtros.m` is **read-only**. It may be moved, but its content must stay the same.
- `LICENSE` stays as it is.
- Documentation is in English.
- Changes go to a dedicated branch and are reviewed through a pull request.

## 4. Success Definition

A reader can learn from the README, in a few minutes, what the project was, what technology it used, how far it got and why it cannot run as it is. The SHA-256 of `src/filtros.m` still matches the original upload.
