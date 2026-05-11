# Preset Manager Line

**Category**: 🧩 Extensions

## Description

A single preset slot inside a Preset Manager. Contains a name text field, an apply button, a save/overwrite button, and a remove button. Spawned automatically by the Preset Manager block.

Each Preset Manager Line represents one stored preset. Click the apply button (or send a jolt to the Trigger input) to restore the preset. Click the save button to overwrite the preset with the current state of the tracked blocks. The name text field can be edited to label the preset.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Preset name | Text Input | Editable text label for this preset slot. |
| Trigger preset | Jolt Input | Apply this preset to the tracked blocks when a jolt is received. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Apply preset | Button | Click to apply this preset to the tracked blocks. |
| Override / Save | Toggle Button | Click to overwrite this preset with the current state of the tracked blocks. |
| Remove preset | Toggle Button | Click to remove this preset slot from the Preset Manager. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Edit text from outside | checkbox | Allows players to edit the preset name text even when this block is inside a group and the player is outside it. |

## Related Blocks

- [preset_manager](/blocks/system/preset_manager)

---