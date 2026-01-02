# Progress Toggle

**Category**: 🎚️ Interfaces

![custom_toggle thumbnail](https://portal.patchxr.io/block-thumbnails/custom_toggle.png)

## Description

Tap to toggle off/on state, sending 0 or 1 from the Jolt output.


Useful for loop or play buttons where you may want to visualize the progress of the loop on the button itself.

To show the on/off state on the progress indicator simply connect the Jolt out to the Progress input.
To drive the progress indicator

## Inputs, Outputs and Parts

**Jolt Out**: Emits 0 or 1 depending on the pressed or upressed state.

**Toggle State**: Send 0 or 1 to set and trigger the pressed or unpressed state.

**Progress**: Fills up a circular progress indicator from 0 to 1. When 0 is received the indicator is empty, when 1 the indicator is full.

---

*Last updated: 2026-01-02 06:20*