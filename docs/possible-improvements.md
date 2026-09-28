# Possible Improvements

[← Back to README](../README.md)

> **None of these improvements have been applied.** The source code is kept exactly as it was originally written to preserve the historical context of the project. This document only lists observations for anyone who might continue the project in a new, separate effort.

## Missing Pieces

| Observation | Impact |
|---|---|
| `filtros.fig` is not in the repository. | The GUI is not expected to open. This is the biggest blocker for running the project. |
| All callbacks are empty. | The application has no image-filtering behavior. |
| There are no sample images or example outputs. | Nobody can see what the intended result looked like. |

## Code-Level Observations

- The control tags mix custom names (`p1`) with GUIDE defaults (`listbox2`, `pushbutton2`). Descriptive tags such as `btnLoadImage` or `lstFilters` would make the code easier to read.
- None of GUIDE's placeholder comments were replaced with a description of what each control is meant to do.

## Platform and Modernization

- **GUIDE is deprecated.** MathWorks recommends **App Designer** (`.mlapp`) for new GUIs. The GUIDE-to-App Designer Migration Tool can convert a `.fig` and `.m` pair, but only if the `.fig` file is found.
- A modern version could put the filters in plain functions (for example grayscale, sepia, blur, edge detection) that are separate from the UI code, so they can be tested and reused.
- Supported MATLAB versions and any required toolboxes (such as the Image Processing Toolbox) should be documented if filter logic is added.

## Repository-Level Suggestions (Optional)

- If the original `filtros.fig` is found, add it to `src/` next to `filtros.m`.
- Add screenshots to an `assets/` folder if the GUI can be run again.
