# Stepped Dial

**Category**: 🎚️ Interfaces

![stepped_dial thumbnail](https://portal.patchxr.io/block-thumbnails/stepped_dial.png)

## Description

Use joystick up/down, or click & drag in any direction to change current step. When a step is changed, its number is emitted from the Jolt output. Add/remove steps in inspector.

Useful to create interfaces that can trigger several different numbers or options in a non-continuous manner (i.e. selecting waveform, presets, octaves). Configure the number of available steps in this block's inspector.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set & Trigger | Jolt Input | Selects the step based on incoming number. E.g. receiving 0 will select the first step of the dial and trigger a 0 from the Jolt output. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Step Out | Jolt Output | Emits the newly selected step when it changes. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Num. steps | text_input | Total number of steps available on the dial (2 to 255). |

## Related Blocks

- [selector_dial](/blocks/interfaces/selector_dial)
- [knob_new](/blocks/interfaces/knob_new)
- [number](/blocks/interfaces/number)
- [cyclecounter](/blocks/logic/cyclecounter)

---