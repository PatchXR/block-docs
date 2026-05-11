# Scaler

**Category**: 🧠 Logic

![keyboard thumbnail](https://portal.patchxr.io/block-thumbnails/keyboard.png)

## Description

A musical keyboard that can be played directly to output MIDI notes, or used as a scale-aware index in edit mode where incoming jolt values select notes from a custom scale.

In play mode the keys output their MIDI note number when pressed. In edit mode you toggle which scale degrees are active, and incoming jolts on the Input port pick the note in the scale at that index (index 0 = root, index 1 = second active note, etc.) with octave wrapping. The root note is set via the dial or the Root note jolt input. Enable 'Sync with global scale' to share root and scale with other keyboards that also have sync enabled.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Jolt Input | Send a jolt to make the keyboard output the MIDI-number of the corresponding note in the scale, starting from zero. E.g. sending 0 will send out the root note, or if you have a major or minor scale selected sending a 2 will output the third. |
| Root note | Jolt Input with Dial | Sets the root note of the keyboard and scale. Maps the "C" key to the chosen note. |
| Root note | Jolt Input | Send a jolt to set the root note of the keyboard and scale. Maps the "C" key to the chosen note. |
| Use Global Scale | Jolt Input | Send >=0.5 to enable global scale sync, <0.5 to disable. When enabled, the keyboard shares its root note and active scale notes with all other keyboards that also have sync enabled. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| MIDI Out | Jolt Output | Outputs the MIDI-number of the key you press, or the corresponding note if you send a jolt to INPUT. |
| Num. notes | Jolt Output | Outputs the number of active notes in the selected scale. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Play/Scale Toggle | Toggle Button | Switches between Play mode (press a key to output its MIDI note) and Scale Edit mode (toggle which notes are active in the scale). |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Sync with global scale | checkbox | When enabled, this keyboard shares its root note and active scale notes with all other keyboards that also have sync enabled. |

## Related Blocks

- [oscillator](/blocks/audio/oscillator)
- [bubble_player](/blocks/audio/bubble_player)
- [metronome](/blocks/logic/metronome)
- [random](/blocks/logic/random)

---