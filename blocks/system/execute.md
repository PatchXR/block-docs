# Execute

**Category**: ⚙️ System

![execute thumbnail](https://portal.patchxr.io/block-thumbnails/execute.png)

## Description

Execute command when triggered. You can reference stream input current values in the command with :1 :2 :3... Ex: bgcolor :1 :2 :3

Runs console commands when triggered via jolt input or button press. Stream inputs can be referenced in commands using placeholders (:1, :2, :3, etc.) to insert current values dynamically. Useful for triggering system functions, changing settings, or executing custom commands.

## Inputs, Outputs and Parts

**text_IN**: Command text to execute when triggered

**esReciver**: Jolt input to trigger command execution

**Button**: Manual button to trigger command execution

**s_IN**: Stream input value (can be referenced as :1 in command)

**Trigger**: Jolt value can be used in console command as :0.

## Related Blocks

- [get_variable](/blocks/system/get_variable)
- [set_variable](/blocks/system/set_variable)

---