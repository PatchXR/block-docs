# Device Box

**Category**: 🎨 Visual

![device_box thumbnail](https://portal.patchxr.io/block-thumbnails/device_box.png)

## Description

A resizable, stylizable box used as the chassis or surface of a device. Drop one inside a group/device and arrange dials, buttons and displays on top of it.

Grab the small handle on the corner to drag the box and resize it. The 'Style' inspector setting picks the visual material (Metal, Plastic, Wood, Glass). Enable 'Lock size' to hide the resize handle once the layout is finished, so players can't accidentally distort the device.

## Inputs, Outputs and Parts

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize | Draggable part | Grab and drag this handle to resize the box on all three axes. Hidden when 'Lock size' is enabled. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Lock size | checkbox | When enabled, hides the resize handle so the box can't be reshaped. Use this once you've finished laying out your device. |
| Style | dropdown | Material/look applied to the box. |

## Related Blocks

- [device_handle](/blocks/controllers/device_handle)
- [landmark](/blocks/system/landmark)

---