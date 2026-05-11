# Joint Piston Output

**Category**: 🧩 Extensions

## Description

Sub-block of "piston". Emits the current position and speed of the piston's linear movement as jolts. Auto-spawned and attached to the parent Piston when the "Outputs" checkbox is enabled in its Inspector.

## Related Wiki Pages

[joint-system](/patching/joint-system)

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Position | Jolt Output | Current offset of the piston along its axis (in meters), relative to the rest position. |
| Speed | Jolt Output | Current slide speed of the piston along its axis (in meters per second). |

## Related Blocks

- [piston](/blocks/motion/piston)
- [joint_piston](/blocks/extensions/joint_piston)
- [joint_piston_limit](/blocks/extensions/joint_piston_limit)

## Tags

DoNotInclude

---