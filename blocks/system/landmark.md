# Device Landmark

**Category**: ⚙️ System

![landmark thumbnail](https://portal.patchxr.io/block-thumbnails/landmark.png)

## Description

Drop one inside a group/device to define its center and forward direction. Used as the spawn alignment when the device is dropped from the library, and as the pivot for kinetic blocks (rotor, joint, etc.).

Without a landmark, a device's pivot defaults to the bounding box center which is rarely what you want for a handheld tool or a rotating mechanism. Place a landmark exactly where you want the pivot and orient it so its forward axis matches the intended 'front'. Toggle 'Freeze Pitch/Roll Rotation' to keep the device upright (useful for UI panels that should never tilt).

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Freeze Pitch Rotation | checkbox | When enabled, the parent device cannot tilt up/down (pitch is locked). Useful for keeping panels or instruments upright. |
| Freeze Roll Rotation | checkbox | When enabled, the parent device cannot tilt left/right (roll is locked). |
| Grid | checkbox | Toggles the global snap-to-grid for the world. Affects every player, not just this device. |

## Related Blocks

- [device_box](/blocks/visual/device_box)
- [device_handle](/blocks/controllers/device_handle)
- [anchor](/blocks/players/anchor)
- [rotor](/blocks/motion/rotor)
- [joint](/blocks/motion/joint)

---