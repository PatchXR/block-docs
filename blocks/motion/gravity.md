# Gravity

**Category**: 🚀 Motion

![gravity thumbnail](https://portal.patchxr.io/block-thumbnails/gravity.png)

## Description

Tweaks the global gravity of the world. Drag the handle to change gravity direction and strength. Snaps back to default Earth gravity (-9.81 m/s²) when released.

Affects every dynamic block in the scene (objects made physical with Make Physical). Useful to create zero-gravity, upside-down, sideways or extra-strong gravity scenarios.

The handle can be dragged in any direction; the magnitude of the gravity vector is proportional to the drag distance from the block. Releasing the handle smoothly interpolates back to the default downward gravity. The handle snaps to perfectly vertical when close, and locks to -9.81 m/s² when very close to it.

If several Gravity blocks are present, the most recently updated one wins. When the block is removed, gravity is restored to Earth default.

## Related Wiki Pages

[physics](/patching/physics)

## Related Blocks

- [make_physical](/blocks/motion/make_physical)
- [make_physical_extra](/blocks/motion/make_physical_extra)
- [field](/blocks/motion/field)
- [thruster](/blocks/motion/thruster)
- [wing](/blocks/motion/wing)

---