# Post Var

**Category**: ⚙️ System

![post_variable thumbnail](https://portal.patchxr.io/block-thumbnails/post_variable.png)

## Description

Push a value (number or text) to Patchworld's online server under a named key. Other worlds, other players, or this same world later, can then read it back with "Fetch Var". Useful for leaderboards, persistent player progress, or recording who visited your world.

The "Can be read from" inspector option controls the visibility scope of the posted value:
- All Worlds: the key is global, every world can read or overwrite it.
- All My Worlds: the key is automatically prefixed with your user id, so only worlds owned by you can access it.
- Only This World: the key is automatically prefixed with the world's product id, so only this exact world can access it.

Tip: combine with the [players](/blocks/players/players) and [get_name](/blocks/system/get_name) blocks to namespace per-player keys (e.g. "PlayerID/HasVisitedMyWorld" = 1, or "PlayerID/Inventory"). This way you can know if a player visited your world from any other world, save per-player scores, or persist a player's inventory across sessions.

Rate limit: this block enforces a soft cap of 10 operations per 10 seconds. When the budget is exceeded, posting is delayed until budget recovers (the "On Done" jolt fires once the operation finally completes).

See the [Online Variables](/wiki/online-variables) wiki page for more details and examples.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Value | Jolt Input with Dial | Numeric value to send to the server. Used when "Value Type" is set to Number. |
| Key | Text Input | Name your variable here, identifies the value on the server. Combine with the world or user prefix (set via the inspector) to scope the key. |
| Text Inputs | Tag Input | Connect text-bearing blocks (e.g. "Txt", "Get Name", "Join & Apply Text") whose contents will be concatenated and sent as the value when "Value Type" is set to Text. |
| Post | Jolt Input | Trigger to send the current value to the server. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| On Done | Jolt Output | Fires 1 once the value has been successfully posted to the server, or 0 if the request failed. Posting may take a moment, especially under rate-limit pressure. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Value Type: | dropdown | Choose between sending a number (using the "Value" dial / jolt) or text (concatenated from the connected "Text Inputs" blocks). |
| Can be read from: | dropdown | Scope of the posted key. - All Worlds: global key, any world can read/write it. - All My Worlds: key is prefixed with your user id (only worlds you own can access). - Only This World: key is prefixed with this world's product id (only this world can access). |
| Edit text from outside | checkbox | When this block is placed inside a Group/Device, its text input is normally only editable from inside the group. Tick this option to let players still click and type into it from outside the group. |

## Related Blocks

- [fetch_variable](/blocks/system/fetch_variable)
- [set_variable](/blocks/system/set_variable)
- [get_variable](/blocks/system/get_variable)
- [players](/blocks/players/players)
- [get_name](/blocks/system/get_name)
- [join_apply_text](/blocks/system/join_apply_text)

---