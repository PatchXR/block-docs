# Player Position

**Category**: 👨‍👩‍👧‍👦 Players

![anchor thumbnail](https://portal.patchxr.io/block-thumbnails/anchor.png)

## Description

Teleport the player to this block's position and orientation when the jolt input fires. Send 0 for an instant jump, or a positive number to lerp over that many seconds.

Useful for spawn points, fast travel, cutscenes, or cockpits. The 'Direction' arrow (the long tube) shows which way the player will face after the teleport. Enable 'Use as spawn position' to make this anchor the spot where players land when joining the world; only one anchor can be set as the spawn at a time. Connect a player to the Tag input (e.g. Players block's 'Nearest Player' output) to teleport only that player; leave unconnected to teleport everyone.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Teleport | Jolt Input | Trigger the teleport. Send 0 for an instant jump, or a positive number for a smooth transition over that many seconds. |
| Restrict Player (optional) | Tag Input | Restrict who gets teleported. When unconnected, every player is teleported. Connect e.g. the 'Nearest Player' output of the Players block to only teleport that specific player. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Direction | Sub Part | The long tube indicates which way the player will be facing after the teleport. Rotate the anchor block to change it. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Use as spawn position | checkbox | When enabled, players entering the world will spawn at this anchor's position and orientation. Only one anchor per world can act as the spawn - enabling this disables it on any other anchor. |
| Triggers on Recenter | checkbox | When enabled, recentering the headset (via the system menu) snaps the player back to this anchor. |
| Swim during teleport | dropdown | How an ongoing swim (locomotion) is handled while the player is lerping toward the anchor. 'Cancels' stops the swim; 'Freezes' pauses input until the teleport ends; 'Ignores' lets the swim continue alongside the teleport. |

## Related Blocks

- [trigger_box](/blocks/players/trigger_box)
- [player_limits](/blocks/players/player_limits)
- [players](/blocks/players/players)
- [controloutput](/blocks/controllers/controloutput)
- [landmark](/blocks/system/landmark)

---