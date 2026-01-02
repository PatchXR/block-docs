# Stepped Dial

**Category**: 🎚️ Interfaces

![stepped_dial thumbnail](https://portal.patchxr.io/block-thumbnails/stepped_dial.png)

## Description

Use joystick up/down, or, click & drag in any direction to change current step. When a step is changed the number of the step will be emitted from the Jolt output. Add/remove steps in inspector.

Useful to create interfaces that can trigger several different numbers or options, in a non continious manner (i.e. selecting waveform, presets, octaves). Configure the number of available steps in this block's inspector.

## Inputs, Outputs and Parts

**Set & Trigger** *(jolt input)*: Selects the step based on incoming number, Ex. Reciving 0 will select the first step of the dial and trigger a 0 from the Jolt output.

**Step Out** *(jolt output)*: Emits the newly selected step when it changes.

---

*Last updated: 2026-01-02 06:41*