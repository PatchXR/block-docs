# Joint Roll Output

**Category**: 🧩 Extensions

## Description

Sub-block of "joint". Emits the current angle and angular speed of the roll rotation (Z axis / blue) as jolts. Auto-spawned and attached to the parent Joint when the Roll "Output Speed & Position" checkbox is enabled in its Inspector.

## Related Wiki Pages

[joint-system](/patching/joint-system)

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Position | Jolt Output | Current roll angle in degrees, in the range [-180; 180]. |
| Speed | Jolt Output | Current roll angular speed (in degrees per second). |

## Related Blocks

- [joint](/blocks/motion/joint)
- [joint_roll](/blocks/extensions/joint_roll)
- [joint_roll_limit](/blocks/extensions/joint_roll_limit)
- [joint_direction_output](/blocks/extensions/joint_direction_output)

## Tags

DoNotInclude

---