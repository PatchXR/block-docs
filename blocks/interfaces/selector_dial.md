# Selector Dial

**Category**: 🎚️ Interfaces

![selector_dial thumbnail](https://portal.patchxr.io/block-thumbnails/selector_dial.png)

## Description

Click & drag in the direction of the desired section to select it, or, use joystick up/down to cycle through the sections clockwise. Configure sections in this block's inspector.

Useful to create very readable interfaces that can trigger several different numbers or options, in a non continious manner (i.e. selecting waveform, presets, octaves). Configure the number of available steps in this block's inspector.

## Inputs, Outputs and Parts

**Section Value**: Emits the value of a section when changed.

Click & pull to generate a new Jolt wire.

**Set & Trigger**: Selects the step based on incoming number, Ex. Reciving 0 will select the first step of the dial and trigger a 0 from the Jolt output.

To connect another block here, click & pull on any Jolt output to create a wire and drag it here.

---

*Last updated: 2026-01-02 06:43*