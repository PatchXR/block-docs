# Envelope

**Category**: 🔊 Audio

![envelope thumbnail](https://portal.patchxr.io/block-thumbnails/envelope.png)

## Description

Generates attack/decay envelopes with adjustable shapes, levels and durations. Trigger to play the envelope and patch the output to modulate a parameter.

Two-stage envelope generator: from a Start value the envelope ramps up to a Mid (peak) value over the Attack Time, then optionally ramps to an End value over the Decay Time. Trigger inputs let you start the attack alone (hold), the decay alone (release), or both back-to-back (single press). The Attack Shape and Decay Shape inspector dropdowns choose between Linear, Exponential, InverseExponential and Soft curves; Decay also supports Infinite (held forever).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Attack Time | Stream Input | How long the attack phase should take (in seconds). |
| Decay Time | Stream Input | How long the decay phase should take (in seconds). |
| Trigger Attack/Decay | Jolt Input | Trigger a full attack followed immediately by a decay. |
| Trigger Attack | Jolt Input | Trigger an attack only. The envelope holds at the peak (Mid value) until a Decay is triggered. |
| Trigger Decay | Jolt Input | Trigger a decay, ramping the envelope from its current value down to the End value. |
| Start value | Jolt Input with Dial | Value the envelope starts from at the beginning of the attack phase. |
| Mid value | Jolt Input with Dial | Peak value reached at the end of the attack phase. |
| End value | Jolt Input with Dial | Value the envelope settles at after the decay phase. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Stream Output | Continuous stream of the envelope's current value. |
| Attack Done | Jolt Output | Emits a jolt when the attack phase finishes. |
| Decay Done | Jolt Output | Emits a jolt when the decay phase finishes. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Trigger | Interactible | Manually trigger an attack+decay (equivalent to sending a jolt on 'Trigger Attack/Decay'). |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Attack Shape | dropdown | Shape of the attack ramp. Linear rises uniformly; Exponential starts slow and accelerates; InverseExponential starts fast and eases out; Soft rounds both ends. Serialization keyword: attackShape |
| Decay Shape | dropdown | Shape of the decay ramp. Same options as Attack Shape, plus Infinite which holds the peak indefinitely until a Trigger Decay is received. Serialization keyword: decayShape |

## Related Blocks

- [oscillator](/blocks/audio/oscillator)
- [metronome](/blocks/logic/metronome)
- [delay_jolt_2](/blocks/logic/delay_jolt_2)
- [function_stream](/blocks/audio/function_stream)

---