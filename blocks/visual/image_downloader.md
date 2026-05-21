# Image Downloader

**Category**: 🎨 Visual

![image_downloader thumbnail](https://portal.patchxr.io/block-thumbnails/image_downloader.png)

## Description

Downloads an image from a URL, an Asset ID, or a Player ID and applies it to a connected Image block.

Connect an Image block to the Target tag input. Provide the URL or ID in the text input. The download happens automatically when the text changes, unless a Jolt is connected to the manual trigger input, in which case it will only download upon receiving a jolt. A jolt is output when the download completes successfully.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Source URL or ID | Text Input | The URL of the image, the Patchworld Asset ID, or the Player ID to download. |
| Image target | Tag Input | Connect an Image block here to apply the downloaded texture. |
| Trigger download | Jolt Input | If connected, the block will only download the image when receiving a jolt here. If disconnected, it downloads automatically when the text changes. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Success output | Jolt Output | Emits a jolt with value 1 when the image has been successfully downloaded and applied. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Max Height Size | dropdown | The maximum vertical resolution to download. Higher values are sharper but use more memory. |
| Type | dropdown | Forces the interpretation of the input text. 'Auto' will try to guess if it's an Asset ID, User ID, or standard URL. |

## Related Blocks

- [image](/blocks/visual/image)
- [players](/blocks/players/players)
- [get_name](/blocks/system/get_name)
- [join_apply_text](/blocks/system/join_apply_text)

---