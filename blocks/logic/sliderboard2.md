# Sliderboard

**Category**: 🧠 Logic

![sliderboard2 thumbnail](https://portal.patchxr.io/block-thumbnails/sliderboard2.png)

## Description

Resizable 2D grid of sliders. Use it as a step sequencer, envelope drawer, mixing console, or addressable numeric memory. Read or write a cell via the Row/Column inputs and the Trigger/Write jolts.

Each cell holds a numeric value controlled by a slider. Drag the resize handle to change the grid dimensions. Select a cell by setting the Row ID and Column ID stream inputs, then fire the Trigger input (or click the trigger button) to emit the stored value, or fire the Write input to overwrite the selected cell with the incoming jolt value. The cell at (Row, Column) highlights in real time.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Row ID | Stream Input | Selects the row to read from or write to (0-indexed). |
| Column ID | Stream Input | Selects the column to read from or write to (0-indexed). |
| Write | Jolt Input | Writes the incoming jolt value into the currently selected cell. |
| Trigger | Jolt Input | Triggers a read: outputs the value of the currently selected cell on the Output. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output value | Jolt Output | Emits the value of the currently selected cell whenever the Trigger input fires. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize | Draggable part | Drag this corner to add or remove rows and columns. |
| Trigger | Interactible | Click to manually trigger a read of the currently selected cell. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Spacing X | slider | Extra horizontal spacing between cells. |
| Spacing Y | slider | Extra vertical spacing between cells. |
| Arrange in group of | integer | Groups cells together every N items, inserting a small gap between groups. Useful for visually splitting steps (e.g. groups of 4). |
| Groups Spacing | slider | Extra gap inserted between groups (paired with 'Arrange in group of'). |
| Interaction Type | dropdown | How players interact with a slider: Trigger (click), Touch (hand contact), or None (read-only). Touch direction options (Begin/Middle/End) define where on the slider the touch is registered. |
| Value Change | dropdown | How the slider value updates: Jump (snaps to the touch position) or Drag (smoothly follows the hand while held). |
| Colorize | dropdown | Selects which part of each slider takes the block's color: Body (full cell) or Indicator (just the fader). |
| Hide Body | checkbox | Hides each slider's body so only the value indicator is visible. |
| Lock Size | checkbox | Hides the resize handle so the grid dimensions can no longer be changed by dragging. |

## Related Blocks

- [toggleboard](/blocks/logic/toggleboard)
- [knobboard](/blocks/logic/knobboard)
- [sliderboard](/blocks/logic/sliderboard)
- [slider_new](/blocks/interfaces/slider_new)
- [data_array](/blocks/logic/data_array)
- [cyclecounter](/blocks/logic/cyclecounter)
- [metronome](/blocks/logic/metronome)

---