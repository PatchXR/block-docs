# Get SubPart

**Category**: ⚙️ System

![get_sub_part thumbnail](https://portal.patchxr.io/block-thumbnails/get_sub_part.png)

## Description

Given a block made of multiple moving parts, outputs a specific sub-part selected by index.

For example, given a player as input, this block can output a specific body part such as the head, the right hand, or a foot. Once a block is connected, the names of its parts are displayed to help pick the right index.

## Related Wiki Pages

[player-inputs](/patching/player-inputs)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input Block | Tag Input | The block (or blocks) from which to select a sub-part. |
| Part Index | Jolt Input with Dial | Sets the index of the part to output. Once a block is connected, the names of its parts are displayed to help you set the right index. |
| Part Name | Text Input | Displays the name and index of the currently selected sub-part. Shows 'Out Of Range' if the index does not match any part on the input block. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Selected Part | Tag Output | Outputs the chosen sub-part of the block given as input. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Edit text from outside | checkbox | When enabled, allows interacting with the text display from outside the group containing this block. |

## Related Blocks

- [players](/blocks/players/players)
- [block_foreach](/blocks/system/block_foreach)
- [all_with_variable](/blocks/system/all_with_variable)
- [get_name](/blocks/system/get_name)

---