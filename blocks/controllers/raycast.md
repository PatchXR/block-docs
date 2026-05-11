# Ray Cast

**Category**: 🎮 Controllers

![raycast thumbnail](https://portal.patchxr.io/block-thumbnails/raycast.png)

## Description

Casts a ray forward and detects the first block(s) it hits. Outputs the hit block(s) and distance, and exposes a second movable part placed on the contact point/normal.

Trigger a ray (or a thicker sphere cast) from the front of the block. When something is hit:
- the **Hit Results** tag output references the block(s) that were hit,
- the **Distance** jolt fires with the distance to the hit point,
- the **Hits Count** jolt fires first with the number of blocks detected (always 1 if Only Output Closest is on),
- the **DestinationMuxPart** movable part snaps to the contact point oriented along the surface normal, so it can be chained with Block Get Position / Set Position / Lookat for visuals or other reactions.

Use **Continuous** to cast every frame, or wire the **Trigger** jolt input to fire on demand. **Min/Max distance** clip results outside the range. Increase **Ray thickness** to perform a sphere cast and grab multiple blocks at once. The optional Tag input can restrict detection to specific blocks (enable *Restrict to blocks* in the Inspector).

Layer toggles in the Inspector control which categories of objects the ray detects: physical blocks, players, hittables, UI, and two block-geometry layers.

## Related Wiki Pages

[physics](/patching/physics)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Restrict (Optional) | Tag Input | When *Restrict to blocks* is enabled in the Inspector, only the blocks connected here are detected by the ray. |
| Min distance | Jolt Input with Dial | Minimum distance (m) at which the ray starts collecting hits. Closer blocks are ignored. |
| Max distance | Jolt Input with Dial | Maximum distance (m) at which the ray stops. Anything further is ignored. |
| Ray thickness | Jolt Input with Dial | Diameter of the ray (m). Above 0, switches to a sphere cast which can hit several blocks side-by-side. |
| Trigger | Jolt Input | Fires the ray cast once (disabled when *Continuous* is ON). |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Hit Results | Tag Output | Tag output: each block hit by the ray. When Only Output Closest is on, only the nearest block is sent; otherwise the outputs fire in order of distance. |
| Distance | Jolt Output | Outputs the distance (m) to each hit block, fired right after the Hit Results tag output is set. |
| Hits Count | Jolt Output | Fired before the other outputs with the total number of blocks hit by the ray (clamped to 1 when Only Output Closest is enabled). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Continuous | Toggle Button | When ON, the ray is cast every frame automatically (the Trigger jolt input is disabled). |
| Hit point | Sub Part | Second movable part of the block. Snaps to the last hit point and is oriented along the surface normal. Use it as a target for Block Get Position / Set Position / Lookat / Follow. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Only Output Closest | checkbox | When ON, only the closest block hit is output. When OFF, all blocks within the ray are output, sorted by distance. |
| Trigger Hittables | checkbox | When ON, the ray simulates a punch on the hit blocks: it triggers their Make Hittable jolts and pushes physical blocks like a real impact would. |
| Restrict to blocks | checkbox | When ON, the ray only detects the blocks connected to the Restrict tag input. |
| Ray Cast Physical | checkbox | When ON, the ray detects physical rigidbodies (blocks made physical via Make Physical, Joint, Piston, etc.). |
| Ray Cast Player | checkbox | When ON, the ray detects player avatars (head, hands, body). |
| Ray Cast Blocks #1 | checkbox | When ON, the ray detects the interactive parts of blocks (knobs, dials, buttons, panels, sliders, etc.). |
| Ray Cast Blocks #2 | checkbox | When ON, the ray detects standard block geometry (visuals, props, terrains). |
| Ray Cast Hittables | checkbox | When ON, the ray detects blocks that have been made hittable via Make Hittable. |
| Ray Cast UI | checkbox | When ON, the ray detects UI elements (menus, panels, etc.). |

## Related Blocks

- [set_hittable](/blocks/motion/set_hittable)
- [make_physical](/blocks/motion/make_physical)
- [block_distance](/blocks/motion/block_distance)
- [block_lookat](/blocks/motion/block_lookat)
- [block_set_position](/blocks/motion/block_set_position)
- [block_relative_position](/blocks/motion/block_relative_position)
- [trigger_box](/blocks/players/trigger_box)

---