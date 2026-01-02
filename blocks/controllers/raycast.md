# Ray Cast

**Category**: 🎮 Controllers

![raycast thumbnail](https://portal.patchxr.io/block-thumbnails/raycast.png)

## Description

Detects blocks in front. Can also measure the distance. It has a second movable part which can be used to collect contact point position & rotation.

## Inputs, Outputs and Parts

**Restrict (Optional)**: Restriction is enabled via inspector. Allow to only "raycast" specific blocks.

**Min distance**: Distance at which the ray start from the block.

**Max distance**: All further block will be ignored.

**Ray thickness**: Make the ray larger, to collect more blocks. (diameter in meter)

**Trigger**: Trigger the ray cast.

**Hit Results**: When collecting a block in front, this output will be set with the target block, and the distance jolt will fire.

**Continuous**: Will trigger the ray automatcially every frame.

**Distance**: When collecting a block in front, tag output will be set with the target block, and this distance jolt will fire.

**Hits Count**: Fired before other output, will output how many blocks the ray hit.

---

*Last updated: 2026-01-02 06:41*