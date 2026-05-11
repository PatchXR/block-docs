# Speedometer

**Category**: 🚀 Motion

![speed thumbnail](https://portal.patchxr.io/block-thumbnails/speed.png)

## Description

Continuously emits the block's speed and acceleration. Use inside a group to make shakers and other instruments that react to movement.

Tracks the position of the block (or group) frame-to-frame and outputs the magnitude of its velocity and acceleration, plus per-axis (X/Y/Z) breakdowns. By default, axes are aligned with the world ('Ignore rotation' on); turn off to use the block's local axes. Includes a jump-limit guard so teleporting the block doesn't produce a spike in the output.

## Related Wiki Pages

[player-inputs](/patching/player-inputs)

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Speed X axis | Jolt Output | Velocity component along the X axis (m/s). |
| Acceleration X axis | Jolt Output | Acceleration component along the X axis (m/s²). |
| Speed | Jolt Output | Total speed (magnitude of the velocity vector) in meters per second. |
| Acceleration | Jolt Output | Total acceleration (magnitude of the acceleration vector) in m/s². |
| Speed Y axis | Jolt Output | Velocity component along the Y axis (m/s). |
| Acceleration Y axis | Jolt Output | Acceleration component along the Y axis (m/s²). |
| Speed Z axis | Jolt Output | Velocity component along the Z axis (m/s). |
| Acceleration Z axis | Jolt Output | Acceleration component along the Z axis (m/s²). |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Ignore rotation | checkbox | When enabled, the per-axis outputs are reported in world coordinates. When disabled, they use the block's local coordinates (so rotating the block changes which world direction each axis tracks). Serialization keyword: ignoreRotation |
| Jump limit | slider | Maximum frame-to-frame distance (in meters) the block can move before being considered teleported. Larger jumps reuse the previous velocity, avoiding spikes when the block is repositioned. Serialization keyword: _jumpLimit |

## Related Blocks

- [position](/blocks/motion/position)
- [block_distance](/blocks/motion/block_distance)
- [block_relative_position](/blocks/motion/block_relative_position)
- [make_physical](/blocks/motion/make_physical)

---