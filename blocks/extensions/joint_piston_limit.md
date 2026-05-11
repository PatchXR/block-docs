# Joint Piston Limit

**Category**: 🧩 Extensions

## Description

Sub-block of "piston". Limits the piston slide to a maximum distance from the rest position. Auto-spawned and attached to the parent Piston when the "Distance Limit" checkbox is enabled in its Inspector.

This sub-block configures the linear distance limit of the parent Piston's ConfigurableJoint. The toggle switches between two modes:
- Springy mode: when the limit is reached, a spring/damper pushes the piston back inside the allowed range.
- Hard mode: the piston hits the limit instantly and bounces back according to the Bounciness value.

## Related Wiki Pages

[joint-system](/patching/joint-system)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Distance Limit | Jolt Input with Dial | Maximum slide distance (in meters) allowed from the rest position. |
| Spring | Jolt Input with Dial | Springy mode only. Stiffness of the spring pushing the piston back inside the allowed range. |
| Inertia | Jolt Input with Dial | Springy mode only. Damping of the limit spring to prevent oscillations when hitting the limit. |
| Bounciness 0-1 | Jolt Input with Dial | Hard mode only. How much the piston bounces back when hitting the limit (0: no bounce, 1: full bounce). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Toggle Mode | Toggle Button | Switches between Springy mode (Spring/Inertia push back) and Hard mode (Bounciness on contact). |

## Related Blocks

- [piston](/blocks/motion/piston)
- [joint_piston](/blocks/extensions/joint_piston)
- [joint_piston_output](/blocks/extensions/joint_piston_output)

## Tags

DoNotInclude

---