# Fetch Var

**Category**: ⚙️ System

![fetch_variable thumbnail](https://portal.patchxr.io/block-thumbnails/fetch_variable.png)

## Description

Pull a value (number or text) previously posted to the server with "Post Var". Use it to load high scores, persistent player progress, or any data shared between worlds.

The "Can be read from" inspector option must match the scope used by the corresponding "Post Var":
- All Worlds: global key.
- All My Worlds: key is prefixed with your user id.
- Only This World: key is prefixed with this world's product id.

Tip: combine with the [players](/blocks/players/players) and [get_name](/blocks/system/get_name) blocks to look up per-player keys (e.g. "PlayerID/HasVisitedMyWorld" or "PlayerID/Inventory"). When fetching text, connect a "Txt" block to the "Text Output" tag input to display the result.

Rate limit: this block enforces a soft cap of 10 operations per 10 seconds. When the budget is exceeded, fetching is delayed until budget recovers.

See the [Online Variables](/wiki/online-variables) wiki page for more details and examples.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Key | Text Input | Name of the variable to read from the server. Must match the key (and scope) used by the corresponding "Post Var". |
| Text Output | Tag Input | Connect text-bearing blocks (e.g. "Txt") here to receive the fetched string when "Value Type" is set to Text. |
| Fetch | Jolt Input | Trigger to request the value from the server. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Fetched Value | Jolt Output | If the key exists on the server, fires its current numeric value (or 1 when fetching text successfully writes to connected Text blocks). |
| On Fail | Jolt Output | Fires 0 when the key does not exist on the server, the request failed, or the rate limit blocked it. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Value Type: | dropdown | Choose between fetching a number (emitted on "Fetched Value") or text (written into the blocks connected to "Text Output"). |
| Can be read from: | dropdown | Scope of the key. Must match the scope used by "Post Var". - All Worlds: global key. - All My Worlds: key is prefixed with your user id (only worlds you own can access). - Only This World: key is prefixed with this world's product id (only this world can access). |
| Edit text from outside | checkbox | When this block is placed inside a Group/Device, its text input is normally only editable from inside the group. Tick this option to let players still click and type into it from outside the group. |

## Related Blocks

- [post_variable](/blocks/system/post_variable)
- [get_variable](/blocks/system/get_variable)
- [set_variable](/blocks/system/set_variable)
- [players](/blocks/players/players)
- [get_name](/blocks/system/get_name)
- [join_apply_text](/blocks/system/join_apply_text)

---