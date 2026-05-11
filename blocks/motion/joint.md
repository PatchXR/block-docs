# Joint

**Category**: 🚀 Motion

![joint thumbnail](https://portal.patchxr.io/block-thumbnails/joint.png)

## Description

Connect two physical parts together and control / constrain their rotation. Useful to build robotic arms, wheels, joysticks, etc.
- Place this joint inside a physical group.
- Connect the Tag input to a different group (or block).
Both groups will be subject to the constraint.
Activate features and degrees of freedom from the Inspector.

The Joint block creates a configurable rotational link between two rigidbodies. Once placed inside a physical group and connected to another part via the Tag input, both parts become attached and follow the joint's constraints.

Degrees of freedom and limits are not built-in: they are added as sub-blocks via the Inspector checkboxes. Each checkbox spawns a dedicated sub-block (joint_direction, joint_roll, joint_direction_limit, joint_roll_limit, joint_direction_output, joint_roll_output) that automatically attaches to the Joint's panel.

For linear (translation) constraints, use the Piston block instead.

## Related Wiki Pages

[joint-system](/patching/joint-system) • [physics](/patching/physics)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Connected Part | Tag Input | Block or group attached to the joint. Will automatically become physical if no "Make Physical" block is used. Only one block or group can be connected at a time. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize the shaft | Draggable part | Drag to resize the visual shaft of the joint. Only affects visuals, not the physics behavior. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
|   XY Axis | checkbox | When ON, spawns and attaches a joint_direction sub-block to control heading and elevation rotation. |
|   Z Axis (Roll) | checkbox | When ON, spawns and attaches a joint_roll sub-block to control roll rotation around the Z axis. |
| Hide Controller | checkbox | When ON, hides the player's controller model while grabbing the connected part. |
| Movement Strength | slider | How strongly the connected part follows the controller's position when grabbed (0-10). |
| Rotation Strength | slider | How strongly the connected part follows the controller's rotation when grabbed (0-10). |
| Lock Size | checkbox | Locks the resize handle so the visual shaft size cannot be changed. |

## Related Blocks

- [piston](/blocks/motion/piston)
- [make_physical](/blocks/motion/make_physical)
- [joint_direction](/blocks/extensions/joint_direction)
- [joint_roll](/blocks/extensions/joint_roll)
- [joint_direction_limit](/blocks/extensions/joint_direction_limit)
- [joint_roll_limit](/blocks/extensions/joint_roll_limit)
- [joint_direction_output](/blocks/extensions/joint_direction_output)
- [joint_roll_output](/blocks/extensions/joint_roll_output)

---