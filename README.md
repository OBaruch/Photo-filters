# Photo Filters (MATLAB GUIDE GUI)

> **Historical repository.** This repository preserves the original implementation of the project. The source code has intentionally not been refactored or modernized in order to retain the historical context and original development approach.

## Project Overview

`Photo-filters` contains a single MATLAB file, [`src/filtros.m`](src/filtros.m), generated with **GUIDE** (MATLAB's legacy GUI Development Environment). *Filtros* is Spanish for *filters*. Together with the repository name, this points to a desktop GUI for applying filters to photos.

The file is a GUIDE **skeleton**. It contains the standard GUIDE initialization code and callback stubs for three UI controls: two push buttons and one list box. None of the callbacks implement any image-processing logic.

## Project Context

| Aspect | Status | Details |
|---|---|---|
| Project origin | **Unknown** | The repository has no assignment, report, course reference or other document that says where the project came from. |
| Author | Confirmed | Baruch Lopez (`LICENSE`, commit history). |
| GUI last edited in GUIDE | Confirmed | `29-Sep-2018 22:31:10` (header comment in `filtros.m`). |
| Uploaded to GitHub | Confirmed | `20-Feb-2021` (commit history). |
| Project type | Inferred | An early-stage or unfinished MATLAB GUI prototype for photo filters. |

More detail: [`docs/project-context.md`](docs/project-context.md).

## Problem Statement

*Inferred:* the project was probably meant to let a user pick an image filter from a list and apply it to a photo through a graphical interface. The code has no implemented behavior that confirms this.

## Objective

*Inferred:* to build an interactive MATLAB GUI where a user selects a filter (list box `listbox2`) and triggers actions (push buttons `p1` and `pushbutton2`), for example loading an image and applying the chosen filter.

## Repository Structure

```
Photo-filters/
├── README.md                     # This file
├── AGENTS.md                     # Guardrails for automated contributors (source is read-only)
├── LICENSE                       # MIT License (original)
├── .gitignore                    # MATLAB editor/autosave artifacts
├── src/
│   └── filtros.m                 # Original GUIDE-generated MATLAB code (unchanged)
└── docs/
    ├── project-context.md        # Origin, timeline and evidence
    ├── code-overview.md          # Walkthrough of filtros.m
    ├── possible-improvements.md  # Observations only, none applied
    └── sdlc/
        ├── intent.md             # Why: reconstructed intent
        ├── spec.md               # What: reconstructed specification and acceptance criteria
        └── plan.md               # How: repository refactor plan and verification
```

## Original Implementation

The source code represents the original implementation of the project. [`src/filtros.m`](src/filtros.m) was moved from the repository root into `src/` with `git mv`. Its content is **byte-for-byte identical** to the original upload (SHA-256 `778a09112953e1be2804532b4d0788e8ca82b75574fe890441c47478b17bdc41`). Nothing was fixed, formatted, renamed or modernized.

## Technologies

| Technology | Evidence |
|---|---|
| MATLAB | `.m` source file, MATLAB syntax. |
| GUIDE v2.5 | Header: `Last Modified by GUIDE v2.5 29-Sep-2018 22:31:10`. |
| MATLAB UI functions | `gui_mainfcn`, `guidata`, `set`/`get`, `ispc`. |

The MATLAB release that was used is **unknown**. The code does not call any Image Processing Toolbox function.

## How It Works

1. Calling `filtros` runs the GUIDE initialization block, which builds a `gui_State` struct and hands it to `gui_mainfcn`.
2. `gui_mainfcn` opens the GUI layout from `filtros.fig`. The GUI is a singleton (`gui_Singleton = 1`).
3. `filtros_OpeningFcn` stores the figure handle in `handles.output` before the window becomes visible.
4. User interactions call the callbacks `p1_Callback`, `listbox2_Callback` and `pushbutton2_Callback`. **All three are empty**, so no filtering happens.

See [`docs/code-overview.md`](docs/code-overview.md) for a function-by-function walkthrough.

## Inputs and Outputs

The original repository does not provide enough information to determine this. It has no sample images, output images or data files, and the callbacks never read or write files.

## Running the Project

> ⚠️ **The GUI layout file `filtros.fig` is not in the repository.**

GUIDE applications need both `filtros.m` and `filtros.fig`. `gui_LayoutFcn` is `[]`, so the layout has to come from the `.fig` file. Without it, the GUI is not expected to open, and the repository cannot be run as it is.

If the original `filtros.fig` is found, put it next to `filtros.m` in `src/`. Then, from MATLAB (the compatible version is unknown):

```matlab
cd src
filtros
```

Note that GUIDE has been deprecated in recent MATLAB releases.

## Documentation

- [Project context](docs/project-context.md)
- [Code overview](docs/code-overview.md)
- [Possible improvements (not applied)](docs/possible-improvements.md)
- Reconstructed SDLC artifacts: [intent](docs/sdlc/intent.md) · [spec](docs/sdlc/spec.md) · [plan](docs/sdlc/plan.md)

## Historical Note

This repository was later reorganized and documented to improve readability and preserve the historical context of the original project. The original source code remains unchanged.

## License

[MIT](LICENSE) © 2021 Baruch Lopez
