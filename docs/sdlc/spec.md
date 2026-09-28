# Specification

[← Back to README](../../README.md) · Previous: [Intent](intent.md) · Next: [Plan](plan.md)

This document has two parts:

- **Part A** specifies the original software *as it exists*, reconstructed from `src/filtros.m`.
- **Part B** specifies the repository reorganization and its acceptance criteria.

Labels: **Confirmed** / **Inferred** / **Unknown**.

---

## Part A: Original Software (As Built)

### A.1 System Overview

A single-window MATLAB GUIDE application. Its entry point is the function `filtros` in `src/filtros.m`.

### A.2 Functional Behavior

| ID | Requirement / behavior | Implemented in code | Status |
|---|---|---|---|
| F-01 | Calling `filtros` opens the GUI window. | GUIDE initialization block (lines 1–44) | Confirmed in code. Needs the missing `filtros.fig`. |
| F-02 | Only one window can exist at a time (singleton). | `gui_Singleton = 1` | Confirmed |
| F-03 | The command line is not blocked while the GUI is open. | `uiwait(handles.figure1)` is commented out | Confirmed |
| F-04 | `H = filtros` returns the figure handle. | `filtros_OutputFcn` | Confirmed |
| F-05 | A list box (`listbox2`) shows selectable options, probably filter names. | `listbox2_Callback` is an empty stub | Control confirmed. Contents unknown. |
| F-06 | On Windows, the list box background is white. | `listbox2_CreateFcn` | Confirmed |
| F-07 | Button `p1` does something when pressed. | `p1_Callback` is an empty stub | Control confirmed. Behavior not implemented. Purpose unknown. |
| F-08 | Button `pushbutton2` does something when pressed. | `pushbutton2_Callback` is an empty stub | Control confirmed. Behavior not implemented. Purpose unknown. |
| F-09 | An image is loaded, filtered and displayed. | — | Inferred from the project name. **Not implemented.** |

### A.3 Interfaces

| Interface | Detail | Status |
|---|---|---|
| Entry point | `filtros`, `H = filtros`, `filtros('Property','Value',...)`, `filtros('CALLBACK',hObject,eventData,handles,...)` | Confirmed (GUIDE header) |
| Layout | `filtros.fig` | Required but **missing** |
| File input/output | None in the code | Confirmed |
| Data formats | — | Unknown |

### A.4 Dependencies and Environment

| Item | Value | Status |
|---|---|---|
| Runtime | MATLAB with GUIDE support | Confirmed |
| MATLAB release | — | Unknown |
| Toolboxes | None called | Confirmed |

### A.5 Known Limitations

- It cannot run as it is, because `filtros.fig` is missing.
- No image-processing features are implemented.

---

## Part B: Repository Reorganization

### B.1 Target Structure

```
README.md
AGENTS.md
LICENSE
.gitignore
src/filtros.m
docs/project-context.md
docs/code-overview.md
docs/possible-improvements.md
docs/sdlc/intent.md
docs/sdlc/spec.md
docs/sdlc/plan.md
```

The following folders are deliberately **left out** because there is no content for them: `data/`, `assets/`, `examples/`, `notebooks/`, `docs/original/`, `archive/`. The project is too small to justify an `architecture.md`, so its structure is covered in `code-overview.md` instead.

### B.2 Acceptance Criteria

| ID | Criterion | How to verify |
|---|---|---|
| AC-01 | The content of `src/filtros.m` is identical to the original `filtros.m`. | `sha256sum src/filtros.m` gives `778a09112953e1be2804532b4d0788e8ca82b75574fe890441c47478b17bdc41` |
| AC-02 | Git records the move as a rename, so the file keeps its history. | `git log --follow src/filtros.m` shows the 2021 upload |
| AC-03 | `LICENSE` is unchanged. | `git diff main -- LICENSE` is empty |
| AC-04 | No files were deleted. | `git diff --diff-filter=D main` is empty |
| AC-05 | The README covers overview, context, problem, objective, structure, original implementation, technologies, how it works, inputs and outputs, running, documentation and historical note. | Manual review |
| AC-06 | Every factual statement is labeled or worded as Confirmed, Inferred or Unknown. | Manual review |
| AC-07 | All relative Markdown links resolve. | Link check |
| AC-08 | No new infrastructure was added (CI, Docker, build tools, test frameworks). | Manual review of the file list |
| AC-09 | All documentation is in English. | Manual review |
