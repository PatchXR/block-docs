# Funnle Stream

**Category**: 🔊 Audio

![reverse_route_stream thumbnail](https://portal.patchxr.io/block-thumbnails/reverse_route_stream.png)

## Description

Combines multiple stream inputs into a single output, selecting which input to route based on an index value.

A dynamic routing block that funnels multiple audio streams into one output. Takes an index input to select which of the multiple stream inputs gets routed to the output. Can be resized to handle more inputs by dragging the resize handle.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Select Index | Stream Input | Select which input to pass to the output. Starting from 0 being the first one. Index values with decimal will mix both inputs together. |
| First Input | Stream Input | First audio stream input. Connect an audio signal here. Routed to the output when index is 0. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Add more Inputs | Draggable part | Click and drag to change the number of inputs. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Lock Size | checkbox | When enabled, prevents the number of inputs from being changed by dragging the resize handle. |

## Related Blocks

- [route](/blocks/logic/route)
- [route_reverse](/blocks/logic/route_reverse)
- [fork](/blocks/connectors/fork)

---