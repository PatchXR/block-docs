# Ruler

**Category**: 🎨 Visual

![ruler thumbnail](https://portal.patchxr.io/block-thumbnails/ruler.png)

## Description

A 2D snap grid for aligning blocks. Drag any block over the grid surface and it snaps to the nearest cell and snap angle.

Useful when arranging buttons, panels, or any layout that needs to be tidy. Drag the corner handle to resize the grid; use the inspector to set the number of rows/lines, the snapping angle (90/60/45/30/22.5°) and to lock the size so players can't accidentally resize it. Snap angle and grid spacing apply to anything dragged within the grid's Z-range.

## Inputs, Outputs and Parts

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize corner | Sub Part | Grab and drag this corner to resize the grid in both axes. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Snapping angle | dropdown | Rotation snap step (degrees) applied when dragging a block over the grid. |
| Rows:  | select_button | +/- to add or remove rows on the X axis. More rows = finer spacing. |
| Lines:  | select_button | +/- to add or remove columns on the Y axis. More columns = finer spacing. |
| Offset up:  | select_button | Shifts the grid plane forward/backward along its Z axis. Useful to align the grid to the top surface of a device. |
| Lock Size | checkbox | When enabled, hides the corner handle so players can't resize the grid. |

## Related Blocks

- [landmark](/blocks/system/landmark)
- [device_box](/blocks/visual/device_box)
- [snapshot](/blocks/visual/snapshot)

---