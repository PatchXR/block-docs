# Pull Blob

**Category**: 🎮 Controllers

![pull_blob thumbnail](https://portal.patchxr.io/block-thumbnails/pull_blob.png)

## Description

Pull a spring-attached blob in 3D space. Emits jolts for the pull length, azimuth angle, and elevation.

An interactive blob attached to its origin by a virtual spring. Grab and drag the blob to displace it: when released, it swings back with simulated spring/damper physics. The block emits three jolt outputs that track the blob's position in real time — pull length, azimuth (horizontal angle), and elevation (vertical offset) — useful for expressive sound or visual modulation.

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Length | Jolt Output | Emits the distance between the blob and its origin (after subtracting a small dead-zone threshold). |
| Azimuth | Jolt Output | Emits the horizontal angle of the blob (0-1, mapped around the full circle). |
| Elevation | Jolt Output | Emits the vertical offset of the blob along the local Y axis. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Pull Handle | Draggable part | Click and drag this handle to displace the blob. When released, the blob swings back to its origin under spring physics. |

## Related Blocks

- [slider](/blocks/interfaces/slider)
- [custom_slider](/blocks/interfaces/custom_slider)
- [knob_new](/blocks/interfaces/knob_new)
- [interaction_box](/blocks/controllers/interaction_box)

---