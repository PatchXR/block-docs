# Midi Mic

**Category**: 🎮 Controllers

![mic thumbnail](https://portal.patchxr.io/block-thumbnails/mic.png)

## Description

Analyzes the microphone input and emits the detected fundamental pitch as a MIDI note number and the amplitude in dB.

Listens to the system microphone and continuously emits two jolts: the detected fundamental pitch (as a MIDI note number) and the signal amplitude (in dB). Useful for driving synths, animations, or game logic from voice or other live sound input.

## Related Wiki Pages

[samples](/patching/samples)

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Note | Jolt Output | Emits the detected fundamental pitch as a MIDI note number. |
| DB | Jolt Output | Emits the signal amplitude of the microphone input, in decibels. |

## Related Blocks

- [microphone](/blocks/audio/microphone)
- [midi_key](/blocks/connectors/midi_key)
- [midi_keys](/blocks/connectors/midi_keys)

---