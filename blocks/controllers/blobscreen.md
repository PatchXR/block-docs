# Blobscreen

**Category**: 🎮 Controllers

![blobscreen thumbnail](https://portal.patchxr.io/block-thumbnails/blobscreen.png)

## Description

Multi-cursor touch screen with blob visuals and a third axis. Each cursor exposes its position, touch and trigger and can record/playback loops, making it a powerful expressive controller.

Resize the screen with the corner handle and add or remove blob cursors with the side handle. Each cursor outputs its normalized X/Y/Z, hover, trigger and crossing events, plus an enabled state and loop progress. Cursors can record loops on the timeline (length in beats) and replay them. Use the num_columns/num_rows dials to subdivide the surface and the fuzz input to add organic noise to the visuals. Great for performative control, drum step patterns or expressive XY/Z modulators.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| fuzz | Jolt Input | Sets the amount of fuzz on the blobs. |
| position_x | jolt input | Sets the X position of the blob. |
| position_y | jolt input | Sets the y position of the blob. |
| position_z | jolt input | Sets the z position of the blob. |
| enabled | jolt input | Send a 1 to enable the blob, 0 to disable.. |
| pulse | jolt input | Send a jolt to make the blob bounce. |
| pulse | jolt input | Send a jolt to make the blob bounce. |
| amp | jolt input | Sets the intensity of the blob. |
| character | jolt input | Sets the character of the blob. |
| blob | jolt input | Sets the blob style/appearance for this cursor. |
| loop | jolt input | Send 1 to enable looping, 0 to disable. |
| loop_select | jolt input | Send jolts with different values to create and recall multiple loops. |
| loop_length | jolt input | Sets the length of the current loop in beats. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| position_x | jolt output | Emits the x position of the blob. |
| position_y | jolt output | Emits the y position of the blob. |
| position_z | jolt output | Emits the z position of the blob. |
| touch | jolt output | Emits a jolt when you touch the blob. |
| trigger | jolt output | Emits how far down the pistol trigger is pressed while grabbing the blob. |
| cross | jolt output | Emits a jolt whenever a blob crosses between two columns. |
| enabled | jolt output | Emits 1 when the blob is enabled and 0 when disabled. |
| loop progress | jolt output | Emits a value between 0 and 1 indicating how far along this blob is in its loop. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize | Draggable part | Drag this handle to change the size of the touch screen. |
| Blobs Count | Draggable part | Drag this handle to add or remove blob cursors. |
| num_columns | Dial | Number of columns drawn on the surface (visual subdivisions). |
| num_rows | Dial | Number of rows drawn on the surface (visual subdivisions). |

## Related Blocks

- [interaction_box](/blocks/controllers/interaction_box)
- [laser_canvas](/blocks/controllers/laser_canvas)
- [pad](/blocks/interfaces/pad)
- [pull_blob](/blocks/controllers/pull_blob)
- [slider_3d](/blocks/controllers/slider_3d)

---