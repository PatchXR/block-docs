# Passthrough

**Category**: 🎨 Visual

![passthrough thumbnail](https://portal.patchxr.io/block-thumbnails/passthrough.png)

## Description

Enables passthrough so the headset's camera feed is displayed around you for a mixed reality experience. The Opacity input fades between full passthrough and the regular VR world.

When active, the world's skybox is replaced by the live camera passthrough from the headset, letting players see their real surroundings while blocks remain visible. Modulate the Opacity input (0 = fully transparent passthrough, 1 = fully opaque passthrough) to blend smoothly between the virtual scene and reality. Requires a passthrough-capable headset.

## Related Wiki Pages

[mr-ar](/patching/mr-ar)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Opacity | Jolt Input with Dial | Passthrough opacity from 0 (no passthrough, normal VR view) to 1 (fully visible real-world passthrough). |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Show handle in playmode | checkbox | Keeps the grab handle visible when players are interacting (playmode). When off, the handle is hidden during play. |
| Always straight | checkbox | Locks the background's vertical axis so it stays upright regardless of how the handle is rotated. |
| Display Background | checkbox | Toggles the passthrough background. When off, the passthrough skybox is not displayed. |

## Related Blocks

- [mixed_reality](/blocks/visual/mixed_reality)
- [ar_window](/blocks/visual/ar_window)
- [magic_window](/blocks/visual/magic_window)
- [vr_window](/blocks/visual/vr_window)
- [magic_spotlight](/blocks/visual/magic_spotlight)

---