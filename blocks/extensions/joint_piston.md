# Joint Piston Control

**Category**: 🧩 Extensions

## Description

Sub-block of "piston". Drives the linear movement along the piston axis with a spring/damper toward a target position and velocity. Auto-spawned and attached to the parent Piston when the "Force & Position" checkbox is enabled in its Inspector.

This sub-block configures the linear X drive of the parent Piston's ConfigurableJoint. Spring pulls the slider toward Target Position; Inertia/Damper applies a force toward Target Velocity and prevents the spring from oscillating. To slide to a position use a non-zero Spring with a Target Position; to slide continuously use a non-zero Inertia with a Target Velocity (and Spring set to 0).

## Related Wiki Pages

[joint-system](/patching/joint-system)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Spring | Jolt Input with Dial | Stiffness pulling the piston toward the Target Position. Higher values reach the target faster. |
| Inertia/Damper | Jolt Input with Dial | Damping that prevents the Spring from wobbling. Also acts as the force pushing toward Target Velocity. |
| Target Position | Jolt Input with Dial | Target offset along the piston axis (in meters). Requires a non-zero Spring to take effect. |
| Target Velocity | Jolt Input with Dial | Target slide speed along the piston axis (in meters per second). Requires a non-zero Inertia, and works best with Spring set to 0. |

## Related Blocks

- [piston](/blocks/motion/piston)
- [joint_piston_limit](/blocks/extensions/joint_piston_limit)
- [joint_piston_output](/blocks/extensions/joint_piston_output)

## Tags

DoNotInclude

---