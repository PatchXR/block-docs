# Joint Roll Control

**Category**: 🧩 Extensions

## Description

Sub-block of "joint". Drives the roll rotation (Z axis) with a spring/damper toward a target angle and angular velocity. Auto-spawned and attached to the parent Joint when the "Z Axis (Roll)" checkbox is enabled in its Inspector.

This sub-block configures the angular X drive of the parent Joint's ConfigurableJoint to control the blue (roll) axis. Spring pulls toward Target Position; Inertia/Damper applies a force toward Target Velocity and prevents the spring from oscillating. To rotate freely use a non-zero Spring with a Target Position; to spin continuously use a non-zero Inertia with a Target Velocity (and Spring set to 0).

## Related Wiki Pages

[joint-system](/patching/joint-system)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Spring | Jolt Input with Dial | Stiffness pulling the joint toward the Target Position. Higher values reach the target faster. |
| Inertia/Damper | Jolt Input with Dial | Damping that prevents the Spring from wobbling. Also acts as the force pushing toward Target Velocity. |
| Target Position | Jolt Input with Dial | Target roll angle (in degrees) the joint tries to reach. Requires a non-zero Spring to take effect. |
| Target Velocity | Jolt Input with Dial | Target roll speed (in degrees per second). Requires a non-zero Inertia to take effect, and works best with Spring set to 0. |

## Related Blocks

- [joint](/blocks/motion/joint)
- [joint_direction](/blocks/extensions/joint_direction)
- [joint_roll_limit](/blocks/extensions/joint_roll_limit)
- [joint_roll_output](/blocks/extensions/joint_roll_output)

## Tags

DoNotInclude

---