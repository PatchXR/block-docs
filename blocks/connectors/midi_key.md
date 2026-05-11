# Midi Key

**Category**: 🔗 Connectors

![midi_key thumbnail](https://portal.patchxr.io/block-thumbnails/midi_key.png)

## Description

Bridges a single MIDI note between Patchworld and an external MIDI app (e.g. a DAW). Sends Note On/Off out when its inputs fire, and emits jolts when the host plays the matching note.

Pick the MIDI channel, note name, and octave in the inspector (or set the note dynamically via the 'Note' jolt input, which accepts a MIDI note number 0-127). The 'Note On' input sends a Note On message with the jolt value as velocity; 'Note Off' sends a Note Off. Conversely, when the host plays the configured note, the matching outputs emit the velocity. Enable 'Send only note on' in the inspector to hide the Note Off output if you don't need release events.

## Related Wiki Pages

[external-connections](/patching/external-connections)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Note On (send) | Jolt Input | Jolt value is sent as the velocity of a MIDI Note On message on the configured channel and note. |
| Note Off (send) | Jolt Input | Jolt value is sent as the velocity of a MIDI Note Off message on the configured channel and note. |
| Note (set) | Jolt Input | Sets the bridged MIDI note number (0-127). Affects both sent and received notes. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Note On (received) | Jolt Output | Emits the velocity (0-127) of an incoming MIDI Note On matching the configured channel and note. |
| Note Off (received) | Jolt Output | Emits the velocity (0-127) of an incoming MIDI Note Off matching the configured channel and note. Hidden when 'Send only note on' is enabled. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Midi channel | integer | MIDI channel to send/receive on (1-16). |
| Note | dropdown | Note name within the octave (C through B, including sharps). |
| Octave | integer | Octave (-2 to 8). Combined with Note, defines the bridged MIDI note number. |
| Send only note on | checkbox | When enabled, the Note Off output is hidden and incoming Note Off messages are ignored. Useful when you only care about triggering events on press. |

## Related Blocks

- [midi_keys](/blocks/connectors/midi_keys)
- [midi_control_change](/blocks/connectors/midi_control_change)
- [mic](/blocks/controllers/mic)
- [keyboard](/blocks/logic/keyboard)

---