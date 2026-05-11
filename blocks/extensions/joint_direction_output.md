# Joint Direction Output

**Category**: 🧩 Extensions

## Description

Sub-block of "joint". Emits the current heading/elevation angles and angular speeds (red and green axes) as jolts. Auto-spawned and attached to the parent Joint when the Direction "Output Speed & Position" checkbox is enabled in its Inspector.

## Related Wiki Pages

[joint-system](/patching/joint-system)

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Position X | Jolt Output | Current heading angle in degrees, in the range [-180; 180]. |
| Speed X | Jolt Output | Current heading angular speed (in degrees per second). |
| Position Y | Jolt Output | Current elevation angle in degrees, in the range [-180; 180]. |
| Speed Y | Jolt Output | Current elevation angular speed (in degrees per second). |

## Related Blocks

- [joint](/blocks/motion/joint)
- [joint_direction](/blocks/extensions/joint_direction)
- [joint_direction_limit](/blocks/extensions/joint_direction_limit)
- [joint_roll_output](/blocks/extensions/joint_roll_output)

## Tags

DoNotInclude

---