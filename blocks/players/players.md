# Players

**Category**: 👨‍👩‍👧‍👦 Players

![players thumbnail](https://portal.patchxr.io/block-thumbnails/players.png)

## Description

Outputs references to players in the world: all players, the local player (yourself), the nearest player, and replay ghosts.

Use the Tag outputs to feed other blocks (Set Position, Set Color, etc.) so they target one or more players. Note that 'ghosts' are recorded replays produced by the Ghost Looper block, not other live players.

## Related Wiki Pages

[player-inputs](/patching/player-inputs)

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| On Player Joined | Jolt Output | Triggered when a new player joins the session. The emitted value is the new total player count. |
| On Player Left | Jolt Output | Triggered when a player leaves the session. The emitted value is the remaining player count. |
| Local Player | Tag Output | Yourself. Warning: in a multiplayer session, every connected player resolves this output to themselves. |
| All Players | Tag Output | Outputs all players, including yourself. |
| All Ghosts | Tag Output | Outputs all ghosts (recorded player replays) currently active in the room. |
| Nearest Player | Tag Output | Outputs the player closest to this block (updated continuously as players move). |

## Related Blocks

- [anchor](/blocks/players/anchor)
- [trigger_box](/blocks/players/trigger_box)
- [ghost_looper](/blocks/players/ghost_looper)
- [users_online](/blocks/players/users_online)
- [get_sub_part](/blocks/system/get_sub_part)

---