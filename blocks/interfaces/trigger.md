# Trigger

**Category**: 🎚️ Interfaces

![trigger thumbnail](https://portal.patchxr.io/block-thumbnails/trigger.png)

## Description

Hit or click to trigger a number (default 1) from the Jolt output.

Can be used as a simple interface button, or a junction point to trigger multiple parts of a patch.

More behavior settings such as output number are available to change in inspector.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Trigger | Jolt Input | Triggers and sends the configured output value (default 1) when receiving any number. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Trig Out | Jolt Output | Sends 1 when triggered (unless value changed in inspector).  Click & pull to generate a new Jolt wire. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Output Value | text_input | The value emitted on the Trig Out jolt output when triggered. |
| Trigger On Click | checkbox | When enabled, pressing the controller trigger while hovering the block fires the output. |
| Trigger On Hit | checkbox | When enabled, physically hitting the block fires the output. |
| Allowed Hit Direction | dropdown | Which direction a hit must come from to trigger the block. 'Front' only accepts hits from the front face; 'Any' accepts hits from all directions. |

## Related Blocks

- [toggle_new](/blocks/interfaces/toggle_new)
- [number](/blocks/interfaces/number)
- [button](/blocks/interfaces/button)
- [pad](/blocks/interfaces/pad)

---