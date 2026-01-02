# Trigger Box

**Category**: 👨‍👩‍👧‍👦 Players

![trigger_box thumbnail](https://portal.patchxr.io/block-thumbnails/trigger_box.png)

## Description

Detects when players enter or exit a resizable area and outputs player count. Can attach players to vehicles when enabled.

Creates a resizable detection zone that tracks player presence. Outputs the number of players currently inside via jolt. Advanced options allow attaching players to vehicles or objects when they enter, with configurable priority system for multiple trigger boxes. Supports player orientation control and separate settings for real players vs ghosts.

## Inputs, Outputs and Parts

**Player inside** *(jolt output)*: Emits the number of players inside the box.

**Resize handle** *(interactive)*: Grab and move to resize the trigger area.

## Related Blocks

- [player_limits](/blocks/players/player_limits)
- [anchor](/blocks/players/anchor)

---