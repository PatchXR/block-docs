# Midi Keys

**Category**: 🔗 Connectors

![midi_keys thumbnail](https://portal.patchxr.io/block-thumbnails/midi_keys.png)

## Description

Bridges polyphonic MIDI notes between Patchworld and an external MIDI app (e.g. a DAW). Like Midi Key, but the note pitch is set via jolts so a single block can handle many notes.

Pick the MIDI channel in the inspector. Drive the 'Note' input with a MIDI note number (0-127) to choose which pitch to send next; 'Note On' / 'Note Off' inputs then send messages on that pitch with the jolt value as velocity. When the host plays a note on the matching channel, the Note output emits the pitch, and Note On / Note Off outputs emit the velocity. Useful for plugging a Scaler/keyboard block into a DAW. Enable 'Monophonic mode' to retrigger the previous held note when the top note is released.

## Related Wiki Pages

[external-connections](/patching/external-connections)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Note (set) | Jolt Input | Sets the bridged MIDI note number (0-127) for the next Note On / Note Off sent out. |
| Note On (send) | Jolt Input | Jolt value is sent as the velocity of a MIDI Note On message on the current note. |
| Note Off (send) | Jolt Input | Jolt value is sent as the velocity of a MIDI Note Off message on the current note. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Note (received) | Jolt Output | Emits the MIDI note number (0-127) of any incoming Note On / Note Off on the configured channel. |
| Note On (received) | Jolt Output | Emits the velocity (0-127) of an incoming MIDI Note On on the configured channel. |
| Note Off (received) | Jolt Output | Emits the velocity (0-127) of an incoming MIDI Note Off on the configured channel. Hidden when 'Send only note on' is enabled. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Midi channel | integer | MIDI channel to send/receive on (1-16). |
| Note | dropdown | Default note name within the octave. Overridden by the 'Note' jolt input when wired. |
| Octave | integer | Default octave (-2 to 8). Overridden by the 'Note' jolt input when wired. |
| Send only note on | checkbox | When enabled, the Note Off output is hidden and incoming Note Off messages are ignored. |
| Monophonic mode | checkbox | When enabled, releasing a held note retriggers the previously held note (last-note-priority mono). Applies to both sent and received notes. |

## Related Blocks

- [midi_key](/blocks/connectors/midi_key)
- [midi_control_change](/blocks/connectors/midi_control_change)
- [keyboard](/blocks/logic/keyboard)
- [mic](/blocks/controllers/mic)

---