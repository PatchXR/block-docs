# Joint Direction Control

**Category**: 🧩 Extensions

## Description

Sub-block of "joint". Drives heading and elevation rotations (red and green axes) with a spring/damper toward target angles and angular velocities. Auto-spawned and attached to the parent Joint when the "XY Axis" checkbox is enabled in its Inspector.

This sub-block configures the angular YZ drive of the parent Joint's ConfigurableJoint. Each of the two axes can be enabled independently with the toggles. Spring pulls each axis toward its Target Position; Inertia/Damper applies a force toward each Target Velocity and prevents the spring from oscillating. To rotate freely use a non-zero Spring with a Target Position; to spin continuously use a non-zero Inertia with a Target Velocity (and Spring set to 0).

## Related Wiki Pages

[joint-system](/patching/joint-system)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Spring | Jolt Input with Dial | Stiffness pulling each enabled axis toward its Target Position. Higher values reach the target faster. |
| Inertia/Damper | Jolt Input with Dial | Damping that prevents the Spring from wobbling. Also acts as the force pushing toward Target Velocity. |
| Target Position (Heading) | Jolt Input with Dial | Target heading angle (in degrees) for the first axis. Requires a non-zero Spring to take effect. |
| Target Velocity (Heading) | Jolt Input with Dial | Target heading speed (in degrees per second) for the first axis. Requires a non-zero Inertia, and works best with Spring set to 0. |
| Target Position (Elevation) | Jolt Input with Dial | Target elevation angle (in degrees) for the second axis. Requires a non-zero Spring to take effect. |
| Target Velocity (Elevation) | Jolt Input with Dial | Target elevation speed (in degrees per second) for the second axis. Requires a non-zero Inertia, and works best with Spring set to 0. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Enable axis 1 (Heading) | Toggle Button | Toggles the first rotation axis on/off (heading). When OFF, this axis is locked. |
| Enable axis 2 (Elevation) | Toggle Button | Toggles the second rotation axis on/off (elevation). When OFF, this axis is locked. |

## Related Blocks

- [joint](/blocks/motion/joint)
- [joint_roll](/blocks/extensions/joint_roll)
- [joint_direction_limit](/blocks/extensions/joint_direction_limit)
- [joint_direction_output](/blocks/extensions/joint_direction_output)

## Tags

DoNotInclude

---