# Join & Apply Text

**Category**: ⚙️ System

![join_apply_text thumbnail](https://portal.patchxr.io/block-thumbnails/join_apply_text.png)

## Description

Combines text from multiple source blocks into one string and applies the result to the target blocks' text. Useful for assembling labels, messages, or commands from dynamic parts.

By default, the output is recalculated automatically whenever a source block's text changes. Connecting a jolt to the Manual Trigger input disables the auto-update so the output is only refreshed when triggered. The Clear jolt empties the result and the target text. Enable 'Accumulate Text' in the inspector to append source texts to the current result on each trigger instead of replacing it.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Source Text | Tag Input | Blocks with text whose contents will be concatenated together in selection order. |
| Manual Trigger | Jolt Input | Connect a jolt here to refresh the output on demand. When connected, the block no longer auto-updates when source blocks change. |
| Target block | Tag Input | Blocks whose text will be replaced by the joined result. |
| Clear | Jolt Input | Clears the result text and the target blocks' text. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Accumulate Text | checkbox | When enabled, each trigger appends the source texts to the current result instead of replacing it. Useful for building a growing log or message. |

## Related Blocks

- [get_name](/blocks/system/get_name)
- [contain_text](/blocks/system/contain_text)
- [set_variable](/blocks/system/set_variable)
- [get_variable](/blocks/system/get_variable)
- [execute](/blocks/system/execute)

---