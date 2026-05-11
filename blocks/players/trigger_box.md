# Trigger Box

**Category**: 👨‍👩‍👧‍👦 Players

![trigger_box thumbnail](https://portal.patchxr.io/block-thumbnails/trigger_box.png)

## Description

Detects when players enter or exit a resizable area and outputs player count. Can attach players to vehicles when enabled.

Creates a resizable detection zone that tracks player presence. Outputs the number of players currently inside via jolt. Advanced options allow attaching players to vehicles or objects when they enter, with configurable priority system for multiple trigger boxes. Supports player orientation control and separate settings for real players vs ghosts.

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Player inside | Jolt Output | Emits the number of players inside the box. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize handle | Draggable part | Grab and move to resize the trigger area. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Ignore ghosts | checkbox | When enabled (default), ghost (recorded/looper) players are not counted as inside the box. |
| Ignore players | checkbox | When enabled, live players are not counted - only ghosts are detected. Mutually useful with 'Ignore ghosts' to target one or the other. |
| Attach players when inside | checkbox | When enabled, the player gets parented to this block while inside (so the player moves with the trigger box - useful for vehicles or moving platforms). Exposes 'Max Attached Players' and 'Attach Priority' below. |
| Max Attached Players | integer | Hard limit on how many players can be attached to this trigger box at once. |
| Attach Priority | integer | Priority used when a player is inside multiple attaching trigger boxes - higher priority wins. Useful for layered vehicles (e.g. a seat inside a cockpit). |
| Tilt upright when inside | checkbox | Forces the player's body to stand upright (no pitch/roll) while inside, even if the trigger box is rotated. |
| Rotation pivot (feet/head) | slider | Sets the pivot used when uprighting the player: 0 = feet, 1 = head. Affects how the body rotates back to upright. |
| Tilt upright when get out | checkbox | When leaving the box, restores the player to an upright orientation. Useful when exiting a tilted vehicle. |

## Related Blocks

- [player_limits](/blocks/players/player_limits)
- [anchor](/blocks/players/anchor)

---