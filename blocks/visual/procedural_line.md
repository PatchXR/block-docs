# Procedural Line

**Category**: 🎨 Visual

![procedural_line thumbnail](https://portal.patchxr.io/block-thumbnails/procedural_line.png)

## Description

Creates dynamic lines with programmable curvature, thickness, and color along the 0-1 progress. Ideal for audio visualization and custom graphics.

Advanced line rendering system that generates lines with customizable properties at each point along its length. Control curvature, thickness, and color based on the line's 0-1 progress parameter. Perfect for audio visualization when combined with Stream Capture blocks to feed real-time audio data into the line parameters. Creates smooth, procedural graphics with fine-grained control.

## Inputs, Outputs and Parts

**X Position** *(stream input)*: Stream input controlling X coordinate along the line (0-1 progress)

**Y Position** *(stream input)*: Stream input controlling Y coordinate along the line (0-1 progress)

**Z Position** *(stream input)*: Stream input controlling Z coordinate along the line (0-1 progress)

**Thickness** *(stream input)*: Stream input controlling line thickness (0-1 progress)

**Color Hue** *(stream input)*: Stream input controlling color hue along the line (0-1 range)

**Color Saturation** *(stream input)*: Stream input controlling color saturation along the line (0-1 range)

**Color Value** *(stream input)*: Stream input controlling color brightness along the line (0-1 range)

**Line Progress** *(stream output)*: Outputs current progress along the line (0-1 ramp)

## Related Blocks

- [stream_capture](/blocks/audio/stream_capture)
- oscilloscope (link not available)
- [spectrum_capture](/blocks/audio/spectrum_capture)

---