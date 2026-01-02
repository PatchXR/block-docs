# Stream Capture

**Category**: 🔊 Audio

![stream_capture thumbnail](https://portal.patchxr.io/block-thumbnails/stream_capture.png)

## Description

Captures and downsamples streams so they can be used with e.g. the procedural_line block.

## Inputs, Outputs and Parts

**Output** *(stream output)*: The value of the internal buffer at the current read cursor position.

**Signal** *(stream input)*: The signal you whish to capture.

**Read cursor** *(stream input)*: Expects a clock going from 0 to 1. The value of the clock determines which part of the internal buffer is read and set to the stream output.

**Window size** *(knob)*: Sets how long it should take to capture one buffer in seconds.

**Mode** *(jolt input)*: Sets the capture mode. 0: rolling, 1: scrolling, 2: paged, 3: zero-cross triggered.

**Freeze** *(jolt input)*: Send a 1 to disable capture and freeze the buffer, 0 to continue capturing.

---

*Last updated: 2026-01-02 06:31*