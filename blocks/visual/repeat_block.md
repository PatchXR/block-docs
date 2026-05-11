# Repeat Block

**Category**: 🎨 Visual

![repeat_block thumbnail](https://portal.patchxr.io/block-thumbnails/repeat_block.png)

## Description

Repeats the visual of any block multiple times, accumulating an offset, rotation and scale between each copy. Great for stairs, fences, flowers, spirals, fractals.

Connect a block to the Tag input, then move the 'From' and 'To' gizmos to define the transform delta between each copy. Set the count, optionally mirror on X/Y/Z, and tune Offset Factor / Chain Stiffness for animated 'whip' or 'follow' behaviour. You can even point a Repeat Block at another Repeat Block to compound patterns. Copies are visual only - they don't run the source block's logic.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Number of copies | Jolt Input with Dial | How many copies of the source block to generate (1-50 with limit on; uncap by disabling 'Count Limit' in the inspector). |
| Mirror X (jolt) | Jolt Input | Toggle the X mirroring via jolt. Any non-zero value flips the state. |
| Mirror Y (jolt) | Jolt Input | Toggle the Y mirroring via jolt. Any non-zero value flips the state. |
| Mirror Z (jolt) | Jolt Input | Toggle the Z mirroring via jolt. Any non-zero value flips the state. |
| Offset Factor | Jolt Input with Dial | Changes the distance between copies. |
| Chain Stiffness | Jolt Input with Dial | 0 to 1 value. Lower = the tip lags/whips behind, higher = the chain is rigid and follows instantly. |
| Color Rush | Jolt Input with Dial | 0 to 1 value. How fast color changes propagate from one copy to the next when 'Spread color' is on. |
| Select block to copy | Tag Input | Click and drag to another block. |

### Others

| Name | Type | Description |
|------|------|-------------|
| To gizmo | Sub Part | Grab and move/rotate/scale this to define the transform applied between successive copies. Position relative to 'From' = translation; rotation relative to 'From' = rotation; scale = added each step. |
| Move control panel | Sub Part | Grab to reposition the control panel without moving the copies. |
| Mirror X | Toggle Button | Click to also mirror all copies along the local X axis (doubles the total count). |
| Mirror Y | Toggle Button | Click to also mirror all copies along the local Y axis (doubles the total count). |
| Mirror Z | Toggle Button | Click to also mirror all copies along the local Z axis (doubles the total count). |
| From gizmo | Sub Part | The starting reference for each copy. The transform difference between 'From' and 'To' is what gets accumulated. You can also tag this with another Repeat Block to chain repetitions. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Spread color | checkbox | When enabled, the source block's color propagates from one copy to the next (rate controlled by Color Rush). |
| Count Limit | checkbox | When enabled (default), the number of copies is capped at 50 for safety. Disable to allow more, but watch out for performance. |

## Related Blocks

- [block_foreach](/blocks/system/block_foreach)
- [block_spawn](/blocks/system/block_spawn)
- [rotor](/blocks/motion/rotor)
- [landmark](/blocks/system/landmark)
- [procedural_line](/blocks/visual/procedural_line)

---