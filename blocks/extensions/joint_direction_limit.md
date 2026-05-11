# Joint Direction Limit

**Category**: 🧩 Extensions

## Description

Sub-block of "joint". Limits the heading and elevation angles (red and green axes) within a symmetric range. Auto-spawned and attached to the parent Joint when the Direction "Angle Limit" checkbox is enabled in its Inspector.

This sub-block configures the angular Y and Z limits of the parent Joint's ConfigurableJoint. Each limit is symmetric around 0 (e.g. a Heading Limit of 30° means [-30°; 30°]). The toggle switches between two modes:
- Springy mode: when the limit is reached, a spring/damper pushes the joint back inside the allowed range.
- Hard mode: the joint hits the limit instantly and bounces back according to the Bounciness value.

## Related Wiki Pages

[joint-system](/patching/joint-system)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Heading Limit | Jolt Input with Dial | Maximum heading angle (in degrees) allowed in either direction (symmetric). |
| Elevation Limit | Jolt Input with Dial | Maximum elevation angle (in degrees) allowed in either direction (symmetric). |
| Spring | Jolt Input with Dial | Springy mode only. Stiffness of the spring pushing the joint back inside the allowed range. |
| Inertia | Jolt Input with Dial | Springy mode only. Damping of the limit spring to prevent oscillations when hitting the limit. |
| Bounciness 0-1 | Jolt Input with Dial | Hard mode only. How much the joint bounces back when hitting the limit (0: no bounce, 1: full bounce). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Toggle Mode | Toggle Button | Switches between Springy mode (Spring/Inertia push back) and Hard mode (Bounciness on contact). |

## Related Blocks

- [joint](/blocks/motion/joint)
- [joint_direction](/blocks/extensions/joint_direction)
- [joint_roll_limit](/blocks/extensions/joint_roll_limit)
- [joint_direction_output](/blocks/extensions/joint_direction_output)

## Tags

DoNotInclude

---