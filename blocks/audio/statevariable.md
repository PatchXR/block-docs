# State Filter

**Category**: 🔊 Audio

![statevariable thumbnail](https://portal.patchxr.io/block-thumbnails/statevariable.png)

## Description

A state variable filter with selectable type, center frequency, and resonance.

Supports 10 filter types, set via the dial or by sending the type index to the Filter Type input: 0: HP (High-Pass), 1: BP (Band-Pass), 2: LP (Low-Pass), 3: UBP (Unit Band-Pass), 4: Notch, 5: AP (All-Pass), 6: Peak, 7: LS (Low Shelf), 8: BS (Band Shelf), 9: HS (High Shelf).

## Related Wiki Pages

[audio-filters](/patching/audio-filters)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Signal input | Stream Input | The input signal. |
| Center frequency | Stream Input | Center frequency of the filter in Hz. Must not be less than 1. |
| Resonance | Stream Input | Resonance of the filter. Must not be less than zero. |
| Filter type | Jolt Input | Sets the filter type by index. 0: HP, 1: BP, 2: LP, 3: UBP, 4: Notch, 5: AP, 6: Peak, 7: LS, 8: BS, 9: HS. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Select Filter | Selector | Choose the filter type using the dial. Options: HP, BP, LP, UBP, Notch, AP, Peak, LS, BS, HS. |

## Related Blocks

- lowpass (link not available)
- highpass (link not available)
- onepole (link not available)
- ladder (link not available)
- [allpass2](/blocks/audio/allpass2)
- [filter](/blocks/audio/filter)
- [filter_eq](/blocks/audio/filter_eq)

---