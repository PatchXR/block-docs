# Contain Text

**Category**: ⚙️ System

![contain_text thumbnail](https://portal.patchxr.io/block-thumbnails/contain_text.png)

## Description

Searches the source text blocks for a specific word or pattern and outputs the number of occurrences found.

By default the search is recomputed automatically whenever the source blocks' text changes. Connecting a jolt to the Manual Trigger input disables auto-update so the result is only refreshed when triggered. Toggle 'Case Sensitive' in the inspector to control whether 'Hello' and 'hello' should count as the same match.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Search pattern | Text Input | The word or pattern to look for inside the source text. If empty, the output is 0. |
| Source Text | Tag Input | Blocks with text whose contents will be concatenated and searched. |
| Manual Trigger | Jolt Input | Connect a jolt here to run the search on demand. When connected, the block no longer auto-updates when source text changes. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Occurrence Count | Jolt Output | Number of times the search pattern was found in the source text. 0 if no match or if the pattern is empty. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Case Sensitive | checkbox | When enabled, 'Hello' and 'hello' are considered different. Disable to match regardless of letter case. |
| Edit text from outside | checkbox | Allows the text input to be clicked and edited from outside the group/device this block belongs to. |

## Related Blocks

- [join_apply_text](/blocks/system/join_apply_text)
- [get_name](/blocks/system/get_name)
- [compare](/blocks/logic/compare)
- [if_else](/blocks/logic/if_else)

---