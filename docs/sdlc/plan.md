# Plan

[← Back to README](../../README.md) · Previous: [Intent](intent.md) → [Spec](spec.md)

This is the step-by-step plan for the repository reorganization defined in the [Spec](spec.md), with the status of each step.

## Phase 1: Discovery ✅

| Step | Action | Result |
|---|---|---|
| 1.1 | List every file in the repository. | 2 files: `LICENSE`, `filtros.m` |
| 1.2 | Read the git history. | 2 commits on 20-Feb-2021 by Baruch Lopez |
| 1.3 | Look for PDF, Word, PowerPoint, images, datasets and outputs. | None found. No visual analysis was needed. |
| 1.4 | Read the full source code. | GUIDE v2.5 scaffold dated 29-Sep-2018, with empty callbacks |
| 1.5 | Record the baseline SHA-256 of `filtros.m`. | `778a0911…b17bdc41` |

## Phase 2: Context Recovery ✅

| Step | Action | Result |
|---|---|---|
| 2.1 | Classify the project origin. | **Unknown**: no documents were found to support any category |
| 2.2 | Build a timeline from the code header and git metadata. | 2018 GUIDE edit, 2021 upload (see [project context](../project-context.md)) |
| 2.3 | List the UI controls from the callback names. | `figure1`, `p1`, `listbox2`, `pushbutton2` |
| 2.4 | Note conflicting or missing information. | The 2018 and 2021 dates differ. `filtros.fig` is missing. |

## Phase 3: Restructure ✅

| Step | Action | Result |
|---|---|---|
| 3.1 | Create a dedicated branch for the pull request. | `docs/repository-refactor` |
| 3.2 | Move `filtros.m` to `src/` with `git mv`. | Recorded as a rename. Content unchanged. |
| 3.3 | Add a minimal MATLAB `.gitignore`. | Autosave and editor backup files only |
| 3.4 | Create only the folders that have content. | `src/`, `docs/`, `docs/sdlc/` |

## Phase 4: Documentation ✅

| Step | Deliverable |
|---|---|
| 4.1 | [`README.md`](../../README.md) |
| 4.2 | [`docs/project-context.md`](../project-context.md) |
| 4.3 | [`docs/code-overview.md`](../code-overview.md) |
| 4.4 | [`docs/possible-improvements.md`](../possible-improvements.md) (observations only) |
| 4.5 | [`docs/sdlc/intent.md`](intent.md), [`spec.md`](spec.md), `plan.md` |
| 4.6 | [`AGENTS.md`](../../AGENTS.md): guardrails for automated contributors |

## Phase 5: Verification ✅

Checked against the acceptance criteria in the [Spec](spec.md#b2-acceptance-criteria):

```bash
sha256sum src/filtros.m                      # AC-01
git log --follow --oneline src/filtros.m     # AC-02
git diff main -- LICENSE                     # AC-03 (empty)
git diff --diff-filter=D --name-only main    # AC-04 (empty)
```

## Phase 6: Review and Merge

Open a pull request from `docs/repository-refactor` to `main`, review it and merge it.

## Out of Scope (Future, Separate Work)

These items are **not** part of this plan. They would need their own intent, spec and plan:

- Finding and adding the original `filtros.fig`.
- Implementing filters or migrating to App Designer (see [possible improvements](../possible-improvements.md)).
