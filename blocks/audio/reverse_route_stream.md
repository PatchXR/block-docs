# Funnle Stream

**Category**: 🔊 Audio

![reverse_route_stream thumbnail](https://portal.patchxr.io/block-thumbnails/reverse_route_stream.png)

## Description

Combines multiple stream inputs into a single output, selecting which input to route based on an index value.

A dynamic routing block that funnels multiple audio streams into one output. Takes an index input to select which of the multiple stream inputs gets routed to the output. Can be resized to handle more inputs by dragging the resize handle.

## Inputs, Outputs and Parts

**Index** *(stream input)*: Selects which input stream to route to the output (0 = first input, 1 = second input, etc.)

**Stream 1** *(stream input)*: First audio stream input

**Output** *(stream output)*: The selected audio stream output

## Related Blocks

- [route](/blocks/logic/route)
- [route_reverse](/blocks/logic/route_reverse)
- [fork](/blocks/connectors/fork)

---