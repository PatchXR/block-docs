# Make Physical Extra

**Category**: 🚀 Motion

![make_physical_extra thumbnail](https://portal.patchxr.io/block-thumbnails/make_physical_extra.png)

## Description

Extra runtime controls for physical blocks: kill velocity/rotation, freeze, reset to edit position, and assign which player simulates the physics.

Make Physical Extra targets blocks that are already physical (typically declared via Make Physical) and exposes runtime actions on them through its **Targets** tag input.

- **Kill velocity** / **Kill Rotation**: instantly zero the linear or angular velocity. Useful to stop runaway motion or reset a vehicle.
- **Freeze** / **Toggle Freeze**: switch the rigidbody to kinematic so it stops responding to forces. Set it to 1 to freeze, 0 to unfreeze.
- **Reset**: teleports the targets back to where they were placed in edit mode (their original position).
- **Sync Now**: forces the local player's physics state to be broadcast to other players (only works if you are the *player in charge* or have recently interacted with the block).
- **Player In Charge**: tag input that designates which player will simulate the physics for the targets. The chosen player sees smooth and consistent motion; others receive a slightly delayed network state. Only one player can be in charge of a given block at a time.

Pair with Make Physical to first declare blocks as physical, then use this block to control them at runtime (e.g. respawn buttons, freeze fields, reset levers, multiplayer ownership transfer).

## Related Wiki Pages

[physics](/patching/physics)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Kill velocity | Jolt Input | Sets the linear velocity of every target rigidbody to zero, stopping its motion instantly. |
| Freeze | Jolt Input | Disable physics on the targets to prevent them from moving (kinematic). 0: physical (unfrozen), 1: frozen. |
| Kill Rotation | Jolt Input | Sets the angular velocity of every target rigidbody to zero, stopping any spin instantly. |
| Sync Now | Jolt Input | Force-broadcast the current physics state of the targets to other players. Only works if you are the player in charge of the block (or have recently interacted with it). |
| Reset | Jolt Input | Teleport the targets back to the position and rotation they had when leaving edit mode. |
| Player In Charge | Tag Input | Designates the player that will simulate the physics for the targets. The in-charge player sees smooth and consistent motion; other players see a slightly delayed network state. Only one player can be in charge at a time. |
| Targets | Tag Input | Blocks or devices that should be affected by these settings (must be physical). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Toggle Freeze | Toggle Button | Toggle freeze on/off. When ON the targets become kinematic and stop responding to physics. |

## Related Blocks

- [make_physical](/blocks/motion/make_physical)
- [set_hittable](/blocks/motion/set_hittable)
- [thruster](/blocks/motion/thruster)
- [field](/blocks/motion/field)
- [wing](/blocks/motion/wing)
- [center_of_mass](/blocks/motion/center_of_mass)
- [joint](/blocks/motion/joint)
- [piston](/blocks/motion/piston)

---