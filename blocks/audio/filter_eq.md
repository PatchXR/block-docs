# Eq Band

**Category**: 🔊 Audio

![filter_eq thumbnail](https://portal.patchxr.io/block-thumbnails/filter_eq.png)

## Description

A filter EQ for boosting or cutting bass, treble, and mid-range frequencies.

## Related Wiki Pages

[audio-filters](/patching/audio-filters)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Stream Input | The audio signal to process. |
| Cutoff Freq | Stream Input | Sets the center frequency where the EQ effect is applied, in Hz. |
| Gain | Stream Input | Controls the amount of boost (values > 1.0) or cut (values < 1.0). The middle position (1.0) has no effect. |
| Steepness | Jolt Input with Dial | Adjusts the sharpness of the EQ curve. Higher values create a more focused, resonant effect. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Stream Output | The filtered audio signal. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Type Dial | Selector | Selects the EQ shape: Low Shelf (bass), High Shelf (treble), or Bell. |

## Related Blocks

- [filter](/blocks/audio/filter)
- [statevariable](/blocks/audio/statevariable)
- [delay](/blocks/audio/delay)

---