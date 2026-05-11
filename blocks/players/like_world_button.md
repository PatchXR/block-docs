# Like World Button

**Category**: 👨‍👩‍👧‍👦 Players

![like_world_button thumbnail](https://portal.patchxr.io/block-thumbnails/like_world_button.png)

## Description

Click to like the world you are visiting. You can only like other people's worlds (not your own).

Toggles a 'like' on the current world (the same like that appears on the published patch page). Owners of the world can't like their own — pressing the button does nothing for them. In multiplayer, when another player likes the world the button still plays its press animation and emits a jolt of 2.

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| On Like/Unlike | Jolt Output | Emits a jolt when the button is pressed. 0 = local player removed their like; 1 = local player liked the world; 2 = another player (in multiplayer) clicked the button. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Like Button | Toggle | Press to toggle your like on this world. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Show Text | checkbox | When enabled, the 'Like' label is shown next to the button. Serialization keyword: _showText |

## Related Blocks

- [users_online](/blocks/players/users_online)
- [anchor](/blocks/players/anchor)
- [players](/blocks/players/players)

---