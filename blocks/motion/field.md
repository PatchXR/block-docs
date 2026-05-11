# Field

**Category**: 🚀 Motion

![field thumbnail](https://portal.patchxr.io/block-thumbnails/field.png)

## Description

Apply a continuous (or pulsed) force to all physical blocks inside its resizable box, or globally in the world.

Field acts as a force volume: any physical block (and optionally physical players) entering its box receives a force determined by the Strength dial.

**Direction mode** controls the shape of the force:
- *Unidirectional*: pushes blocks along the arrow direction.
- *Outward*: pushes blocks away from the field's center (or attracts when Strength is negative).
- *Whirling*: rotates blocks around the field's axis.

**Trigger Mode** controls when the force is applied: Continuously every frame, on Jolt (when the Strength input receives a value), on Enter or on Exit (one-shot impulse when a block enters/leaves the box).

Use the **Only Include** tag input to restrict the field to specific blocks, or **Exclude** to ignore some. Enable **Is Global** to drop the box entirely and apply the force to every physical block in the world (useful for global gravity, global wind, etc.).

Useful for wind, gravity wells, water buoyancy, magnetic attractors, explosions, conveyor belts, and any volumetric force effect.

## Related Wiki Pages

[physics](/patching/physics)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Strength | Jolt Input with Dial | Magnitude of the force applied to blocks inside the field. In Jolt trigger mode, this also acts as the trigger: each value received fires one impulse. |
| Only Include | Tag Input | When connected, the field only affects these blocks (others inside the box are ignored). When empty, the field affects every physical block inside the box. |
| Exclude | Tag Input | Blocks connected here are ignored by the field, even when inside the box. |
| Is Global | Jolt Input | When set to >0.5, the field is applied to all physical blocks in the world (the box is hidden). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize | Draggable part | Drag to resize the box of the field. |
| Direction | Sub Part | Movable arrow indicating the direction of the force (in Unidirectional mode), or the axis of rotation (in Whirling mode). Has no effect in Outward mode. |
| Is Global | Toggle Button | When ON, the field affects all physical blocks in the world (the box is hidden). |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Trigger Mode | dropdown | When the force is applied: Continuous (every frame), Jolt (each value received on Strength), Enter (one impulse when a block enters the box) or Exit (one impulse when a block leaves the box). |
| Direction | dropdown | Shape of the force: Unidirectional pushes along the arrow, Outward pushes from the center (or attracts with negative strength), Whirling rotates around the axis. |
| Ignore Mass | checkbox | When ON, the force is applied as Acceleration (or VelocityChange in impulse modes), so heavy blocks accelerate the same as light ones. |
| Do Not Affect Rotation | checkbox | When ON, the force is applied at the center of mass of each rigidbody assembly so it produces no torque. Without this, the off-center force may cause the block to spin. |
| Affects Physical Players | checkbox | When ON, players that have been made physical (e.g. via Make Physical's Affects Player option) are also pushed by the field. |

## Related Blocks

- [make_physical](/blocks/motion/make_physical)
- [make_physical_extra](/blocks/motion/make_physical_extra)
- [thruster](/blocks/motion/thruster)
- [wing](/blocks/motion/wing)
- [center_of_mass](/blocks/motion/center_of_mass)
- [trigger_box](/blocks/players/trigger_box)
- [joint](/blocks/motion/joint)
- [piston](/blocks/motion/piston)

---