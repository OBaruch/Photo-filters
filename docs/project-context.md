# Project Context

[← Back to README](../README.md)

This document collects everything the repository says about where the project came from. Each statement is labeled:

- **Confirmed**: directly supported by a file or by the git history.
- **Inferred**: a reasonable deduction from the available evidence.
- **Unknown**: cannot be determined from the repository.

## Project Origin

**Project origin: Unknown**

The repository contains no PDF, Word document, presentation, report, assignment statement, course code, university name or README from the original project. There is not enough evidence to classify it as academic coursework, a personal project or an experiment. It is therefore labeled *Unknown*, and no context has been invented.

## Evidence Inventory

The original repository had two commits and two files:

| File | Type | Role |
|---|---|---|
| `LICENSE` | Text | MIT License, `Copyright (c) 2021 Baruch Lopez`. |
| `filtros.m` | MATLAB source (110 lines) | GUIDE-generated GUI code. Now at [`src/filtros.m`](../src/filtros.m). |

It had no images, datasets, outputs, notebooks, configuration files or documentation.

## Timeline

| Date | Event | Source | Status |
|---|---|---|---|
| 29-Sep-2018 22:31:10 | GUI layout last modified in GUIDE v2.5 | Header comment in `filtros.m` | Confirmed |
| 20-Feb-2021 | GitHub repository created ("Initial commit": `LICENSE`) | Git history | Confirmed |
| 20-Feb-2021 | `filtros.m` uploaded ("Add files via upload") | Git history | Confirmed |
| Later | Repository reorganized and documented, source unchanged | This branch | Confirmed |

**Note on the dates:** the code was last edited in GUIDE about two and a half years before it was uploaded. Most likely the project was written in 2018 and archived on GitHub in 2021. That is an inference, not a confirmed fact.

## What the Project Was About

| Question | Answer | Status |
|---|---|---|
| Domain | Photo / image filters | Inferred from the repository name `Photo-filters` and the file name `filtros` (Spanish for "filters"). |
| Technology | MATLAB with a GUIDE GUI | Confirmed |
| Language of the author's naming | Spanish (`filtros`) | Confirmed |
| Intended user interaction | Pick an option from a list box and press buttons | Inferred from the UI controls `listbox2`, `p1` and `pushbutton2`. |
| Implemented filters | None | Confirmed: every callback is empty. |
| Which filters were planned | — | Unknown |
| Whether the project was finished elsewhere | — | Unknown |
| Academic or personal | — | Unknown |

## Scope and State

- **Confirmed:** the uploaded code is a GUIDE scaffold. It has the standard initialization, opening and output functions, plus empty callbacks for three controls.
- **Confirmed:** the GUIDE layout file `filtros.fig` was never committed.
- **Inferred:** the upload is an early snapshot of the project, or a partial one. Any image-processing logic either lived elsewhere or was never written.

## Related Documents

- [Code overview](code-overview.md)
- [Possible improvements](possible-improvements.md)
- [Intent](sdlc/intent.md) · [Spec](sdlc/spec.md) · [Plan](sdlc/plan.md)
