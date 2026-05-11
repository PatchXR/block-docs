# Constant

**Category**: 🧠 Logic

![constant thumbnail](https://portal.patchxr.io/block-thumbnails/constant.png)

## Description

Outputs a chosen math or system constant on the Jolt output. Available constants: π, sample rate, sample period, e (Euler's number), tempo (BPM), beat time, golden ratio, and Play Mode (1 in play, 0 in edit).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Trigger | Jolt Input | Send any jolt to fire the output with the currently selected constant. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the value of the selected constant whenever it changes, or whenever a jolt is received on the Trigger input. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Constant | Selector | Selects which constant to output: π, Sample rate, Sample period, e, Tempo (BPM), Beat time, Golden ratio, or Play Mode. |

## Related Blocks

- [operation](/blocks/logic/operation)
- [function](/blocks/logic/function)
- [get](/blocks/logic/get)
- [rhythm](/blocks/audio/rhythm)
- [number](/blocks/interfaces/number)

---