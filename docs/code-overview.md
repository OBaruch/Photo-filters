# Code Overview

[← Back to README](../README.md)

This document explains [`src/filtros.m`](../src/filtros.m) without changing it. Line numbers refer to the original, unmodified file.

## File Summary

| Property | Value |
|---|---|
| Path | `src/filtros.m` |
| Language | MATLAB |
| Lines | 110 |
| Generator | GUIDE v2.5 (`Last Modified by GUIDE v2.5 29-Sep-2018 22:31:10`) |
| Companion file needed | `filtros.fig` (**missing** from the repository) |
| Hand-written logic | None found. All content matches the standard GUIDE template. |

## How a GUIDE Application Is Put Together

A GUIDE application is made of two files:

1. **`filtros.fig`** holds the window layout: controls, positions, labels and list items. The layout is built visually in GUIDE.
2. **`filtros.m`** holds the entry point and one callback function per UI event.

`gui_LayoutFcn` is set to `[]`. This means the layout is not generated from code, so `gui_mainfcn` has to load it from `filtros.fig`.

```
User runs `filtros`
        │
        ▼
filtros(varargin) ── builds gui_State ──► gui_mainfcn
                                           │
                     loads filtros.fig ◄───┘ (file missing)
                                           │
                                           ▼
                                 filtros_OpeningFcn
                                           │
                                           ▼
                                 filtros_OutputFcn ──► returns figure handle
                                           │
                  UI events ──► p1_Callback / listbox2_Callback / pushbutton2_Callback
                                (all empty)
```

## Functions

### `filtros(varargin)`, lines 1–44: entry point

- The standard GUIDE initialization block, marked `DO NOT EDIT`.
- `gui_Singleton = 1` allows only one window at a time. Calling `filtros` again brings the existing window to the front.
- If the first argument is a string, it is treated as the name of a callback to dispatch (`str2func(varargin{1})`). This is how the `.fig` file calls the callbacks.
- Delegates everything to `gui_mainfcn`.

### `filtros_OpeningFcn(hObject, eventdata, handles, varargin)`, lines 47–62

- Runs just before the window becomes visible.
- Sets `handles.output = hObject` and saves the handles with `guidata`.
- `uiwait(handles.figure1)` is commented out, so the GUI does not block the command line. This also shows that the main figure's tag is `figure1`.

### `filtros_OutputFcn(hObject, eventdata, handles)`, lines 65–73

- Returns `handles.output` (the figure handle) to the caller.

### `p1_Callback(hObject, eventdata, handles)`, lines 76–80

- Runs when the push button tagged **`p1`** is pressed.
- **Empty body.** The control was renamed from GUIDE's default name (`pushbutton1`) to `p1`, which suggests the author had a role in mind for it. That role is **unknown**.

### `listbox2_Callback(hObject, eventdata, handles)`, lines 83–90

- Runs when the selection in the list box tagged **`listbox2`** changes.
- **Empty body.** Only GUIDE's hint comments on reading the selection are there.
- *Inferred:* this list probably held the names of the available filters.

### `listbox2_CreateFcn(hObject, eventdata, handles)`, lines 93–103

- Runs when the list box is created.
- Standard GUIDE code: on Windows, sets the list box background to white if it still uses the default color.

### `pushbutton2_Callback(hObject, eventdata, handles)`, lines 106–110

- Runs when the push button tagged **`pushbutton2`** is pressed.
- **Empty body.** Its purpose is **unknown**. It could have been meant for applying a filter or loading an image.

## UI Controls Found in the Code

| Tag | Control type | Evidence | Behavior |
|---|---|---|---|
| `figure1` | Main window | Commented `uiwait(handles.figure1)` | Hosts the GUI. |
| `p1` | Push button | `p1_Callback` | Not implemented |
| `listbox2` | List box | `listbox2_Callback`, `listbox2_CreateFcn` | Only sets the background color on Windows |
| `pushbutton2` | Push button | `pushbutton2_Callback` | Not implemented |

Other controls may exist in `filtros.fig`, such as axes for showing images or static text labels. GUIDE only writes callbacks for controls that have them, so the list above may be incomplete. This **cannot be confirmed** because the `.fig` file is missing.

## Dependencies Observed

- Core MATLAB only: `gui_mainfcn`, `guidata`, `str2func`, `get`, `set`, `ispc`, `isequal`.
- No toolbox functions are called. The Image Processing Toolbox is not used.
