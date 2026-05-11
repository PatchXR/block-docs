# Vr Window

**Category**: 🎨 Visual

![vr_window thumbnail](https://portal.patchxr.io/block-thumbnails/vr_window.png)

## Description

Resizable plane that reveals the virtual scene through passthrough. Use it together with the passthrough or mixed_reality block to cut a window of VR into the real world.

Acts as a stencil: while passthrough is active, the area covered by this plane shows the virtual world instead of the real one. Drag the corner handle to resize the window. Pair with mixed_reality or passthrough to create framed VR portals into the user's room.

## Inputs, Outputs and Parts

### Others

| Name | Type | Description |
|------|------|-------------|
| Display Plane | Interactible | The window surface that reveals the virtual scene when passthrough is active. |
| Resize Handle | Draggable part | Drag this corner with the trigger to resize the window. |

## Related Blocks

- [ar_window](/blocks/visual/ar_window)
- [magic_window](/blocks/visual/magic_window)
- [passthrough](/blocks/visual/passthrough)
- [mixed_reality](/blocks/visual/mixed_reality)

---