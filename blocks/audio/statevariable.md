# statevariable

**Category**: 🔊 Audio

![statevariable thumbnail](https://portal.patchxr.io/block-thumbnails/statevariable.png)

## Description

A state variable filter, with center frequency, resonance and filter type settings.

## Inputs, Outputs and Parts

**Signal input** *(stream input)*: The input signal.

**Center frequency** *(stream input)*: Center frequency of the filter (in Hz). Must not be less than one.

**Resonance** *(stream input)*: Resonance of the filter. Must not be less than zero.

**Filter type** *(jolt input)*: Sets the type of the filter. 0:HP, 1:BP, 2:LP, 3:UBP, 4:Notch, 5:AP, 6:Peak, 7:LS, 8:BS, 9:HS

## Related Blocks

- [lowpass](/blocks/lowpass)
- [highpass](/blocks/highpass)
- [onepole](/blocks/onepole)
- [ladder](/blocks/ladder)
- [allpass2](/blocks/allpass2)

---

*Last updated: 2026-01-02 05:47*