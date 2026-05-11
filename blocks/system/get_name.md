# Get Name Text

**Category**: ⚙️ System

![get_name thumbnail](https://portal.patchxr.io/block-thumbnails/get_name.png)

## Description

Outputs the name of the source blocks as text. If multiple blocks are given, names are separated by a comma and whitespace. Also works on players and devices.

The 'Output Mode' dropdown selects what is written into the text output: 'Name' (display name), 'Techy Name' (internal MuXObject identifier, useful for scripting), 'Asset ID', 'Asset URL', 'Asset Path', or 'Asset URL or Path' (returns URL when available, otherwise the local path). Asset modes only return a value on asset-backed blocks such as imported models, image sequences, 360 images, video clips, or devices.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Source Block | Tag Input | Blocks (or players / devices) whose name will be written into this block's text. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Output Mode | dropdown | Selects what kind of name/identifier is written out. 'Name': display name (or player's actual name). 'Techy Name': internal MuXObject identifier. 'Asset ID' / 'Asset URL' / 'Asset Path' / 'Asset URL or Path': metadata for asset-backed blocks (imported model, image, video, device). |

## Related Blocks

- [join_apply_text](/blocks/system/join_apply_text)
- [contain_text](/blocks/system/contain_text)
- [set_variable](/blocks/system/set_variable)
- [get_variable](/blocks/system/get_variable)

---