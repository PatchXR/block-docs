# Collider

**Category**: 🎚️ Interfaces

![collider thumbnail](https://portal.patchxr.io/block-thumbnails/collider.png)

## Description

An invisible hittable sphere that emits the impact velocity whenever something physical bumps into it. Use it to build mallets, beaters, drumsticks, swords, or any tool that needs to react to contact.

Filters out collisions caused by blocks in the same group/device so a mallet doesn't trigger itself. Best paired with the Make Physical block on the object you want to hit, and an Output/Bubble block to play a sound on impact. The sphere itself is invisible at runtime - put it inside a device with a visible mesh to give it a body.

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Collision | Jolt Output | Emits the relative velocity magnitude every time the sphere collides with another physical object. Higher = harder hit. |

## Related Blocks

- [make_physical](/blocks/motion/make_physical)
- [set_hittable](/blocks/motion/set_hittable)
- [pad](/blocks/interfaces/pad)
- [block_watcher](/blocks/system/block_watcher)
- [saber](/blocks/controllers/saber)

---