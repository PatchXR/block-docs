# Joint Roll Limit

**Category**: 🧩 Extensions

## Description

Sub-block of "joint". Limits the roll angle (Z axis / blue) between a low and a high boundary. Auto-spawned and attached to the parent Joint when the Roll "Angle Limit" checkbox is enabled in its Inspector.

This sub-block configures the angular X limits of the parent Joint's ConfigurableJoint. The toggle switches between two modes:
- Springy mode: when the limit is reached, a spring/damper pushes the joint back inside the allowed range.
- Hard mode: the joint hits the limit instantly and bounces back according to the Bounciness value.

## Related Wiki Pages

[joint-system](/patching/joint-system)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Low angle | Jolt Input with Dial | Lowest allowed roll angle (in degrees). Will be clamped to the High angle if greater. |
| High Angle | Jolt Input with Dial | Highest allowed roll angle (in degrees). |
| Spring | Jolt Input with Dial | Springy mode only. Stiffness of the spring pushing the joint back inside the allowed range. |
| Inertia | Jolt Input with Dial | Springy mode only. Damping of the limit spring to prevent oscillations when hitting the limit. |
| Bounciness 0-1 | Jolt Input with Dial | Hard mode only. How much the joint bounces back when hitting the limit (0: no bounce, 1: full bounce). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Toggle Mode | Toggle Button | Switches between Springy mode (Spring/Inertia push back) and Hard mode (Bounciness on contact). |

## Related Blocks

- [joint](/blocks/motion/joint)
- [joint_roll](/blocks/extensions/joint_roll)
- [joint_direction_limit](/blocks/extensions/joint_direction_limit)
- [joint_roll_output](/blocks/extensions/joint_roll_output)

## Tags

DoNotInclude

---