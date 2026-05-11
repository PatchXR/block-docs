# Execute

**Category**: ⚙️ System

![execute thumbnail](https://portal.patchxr.io/block-thumbnails/execute.png)

## Description

Runs a console command when triggered. Reference stream input values in the command with :1 :2 :3..., and the jolt value with :0. Example: bgcolor :1 :2 :3 (see wiki.patchxr.io/en/patching/console-commands).

Runs console commands when triggered via jolt input or button press. Stream inputs can be referenced in commands using placeholders (:1, :2, :3, etc.) to insert current values dynamically. Useful for triggering system functions, changing settings, or executing custom commands.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Command | Text Input | Command text to execute when triggered. Supports :0 (jolt value) and :1, :2, :3, :4 (stream input values) placeholders. |
| Trigger | Jolt Input | Triggers the command. The incoming jolt value can be inserted into the command using :0 (e.g. "changeFogDistance :0"). |
| Input :1 | Stream Input | Stream input referenced as :1 in the command. |
| Input :2 | Stream Input | Stream input referenced as :2 in the command. |
| Input :3 | Stream Input | Stream input referenced as :3 in the command. |
| Input :4 | Stream Input | Stream input referenced as :4 in the command. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Trigger | Interactible | Hit or click to run the command. Jolt value can be used in the command as :0. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Execute for local player only | toggle | When enabled, the command only runs for the local player who triggered it (not for other players in multiplayer). Useful for actions like teleportation that shouldn't affect everyone. |
| Edit text from outside | checkbox | Allows the command text to be edited by players outside a group/device that contains this block. |

## Related Blocks

- [get_variable](/blocks/system/get_variable)
- [set_variable](/blocks/system/set_variable)
- [trigger](/blocks/interfaces/trigger)
- [post_variable](/blocks/system/post_variable)
- [fetch_variable](/blocks/system/fetch_variable)

---