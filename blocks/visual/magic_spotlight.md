# Magic Spotlight

**Category**: 🎨 Visual

![magic_spotlight thumbnail](https://portal.patchxr.io/block-thumbnails/magic_spotlight.png)

## Description

A spotlight that reveals the real world through passthrough wherever its beam shines. Toggle on/off and modulate its intensity via the jolt input.

Use it together with the mixed_reality block to dynamically punch a beam of passthrough into the virtual scene. The jolt input acts as an intensity modulator: feeding non-zero values controls how brightly the spotlight reveals the real world. Useful for theatrical effects mixing virtual content with the physical room.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Intensity | Jolt Input | Sets the spotlight intensity. 0 turns it off, higher values make it brighter. |

### Others

| Name | Type | Description |
|------|------|-------------|
| On/Off | Toggle Button | Toggle the spotlight on or off. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Show outlines | checkbox | Display outlines around detected real-world furniture (shared mixed reality setting). |

## Related Blocks

- [mixed_reality](/blocks/visual/mixed_reality)
- [passthrough](/blocks/visual/passthrough)
- [magic_window](/blocks/visual/magic_window)
- [lightbulb](/blocks/visual/lightbulb)
- [sunlight](/blocks/visual/sunlight)

---