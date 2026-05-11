# Player Limits

**Category**: 👨‍👩‍👧‍👦 Players

![player_limits thumbnail](https://portal.patchxr.io/block-thumbnails/player_limits.png)

## Description

Defines a resizable cubic boundary that players cannot move outside of. Useful for keeping people in a play area, a room, or a stage.

Drag the corner handle to resize the boundary. The Enable jolt input lets you turn the restriction on/off at runtime (e.g. open a 'door' once a puzzle is solved). The boundary is invisible to players once the world is published.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Enable | Jolt Input | Turn the boundary on (non-zero) or off (0). When off, players can move freely through it. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize Handle | Draggable part | Grab and drag to resize the boundary on all three axes. |

## Related Blocks

- [trigger_box](/blocks/players/trigger_box)
- [anchor](/blocks/players/anchor)

---