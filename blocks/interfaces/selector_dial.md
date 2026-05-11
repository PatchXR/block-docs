# Selector Dial

**Category**: 🎚️ Interfaces

![selector_dial thumbnail](https://portal.patchxr.io/block-thumbnails/selector_dial.png)

## Description

Click & drag in the direction of the desired section to select it, or use joystick up/down to cycle through the sections clockwise. Configure sections in this block's inspector.

Useful to create very readable interfaces that can trigger several different numbers or options, in a non-continuous manner (i.e. selecting waveform, presets, octaves). Configure the number of available steps in this block's inspector.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set & Trigger | Jolt Input | Selects the section based on incoming index. E.g. receiving 0 will select the first section of the dial and trigger that section's value from the Jolt output.  To connect another block here, click & pull on any Jolt output to create a wire and drag it here. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Section Value | Jolt Output | Emits the value of a section when changed.  Click & pull to generate a new Jolt wire. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Select | Selector | Click & drag toward a section to select it. Emits the value corresponding to the selected option (starting from index 0). |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Section Count | integer | Number of sections on the dial (2 to 20). Adding or removing sections creates or trims the Label / Value entries below. |
| Label #0 | text_input | Display label shown on this section of the dial. |
| Value #0 | text_input | Number emitted from the Section Value output when this section is selected. |
| Label #1 | text_input | Display label shown on this section of the dial. |
| Value #1 | text_input | Number emitted from the Section Value output when this section is selected. |

## Related Blocks

- [stepped_dial](/blocks/interfaces/stepped_dial)
- [number](/blocks/interfaces/number)
- [selector_gate](/blocks/connectors/selector_gate)
- [knob_new](/blocks/interfaces/knob_new)

---