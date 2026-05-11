# Toggle

**Category**: 🎚️ Interfaces

![toggle_new thumbnail](https://portal.patchxr.io/block-thumbnails/toggle_new.png)

## Description

Hit or click inside to change off/on state, sending 0 or 1 by default from the Jolt output.


Can be edited and used in many ways to switch states of other blocks.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Set state | Jolt Input | Send a jolt message to change the on/off state of the toggle. By default, any number will flip current state. Check this block's Inspector to change its input and output behavior.  To connect another block here, click & pull on any Jolt output to create a wire and drag it here. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| State out | Jolt Output | Sends 0-1 (by default) depending on the toggle state. Click inside the cube to switch the output number.  Click & pull to generate a new Jolt wire. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Input Mode | dropdown | How the Set state input behaves: 'Toggle' flips the state on every received jolt; 'Set' sets the state to match the incoming value (>=0.5 = on, <0.5 = off). |
| Off Value | text_input | The value emitted on the State out jolt output when the toggle is off. |
| On Value | text_input | The value emitted on the State out jolt output when the toggle is on. |
| Interaction Type | dropdown | How the user toggles state. 'Trigger' = press the controller trigger; 'Touch' = physically touch the block; 'None' = no manual interaction (jolt input only). |
| Momentary | checkbox | When enabled, the toggle stays on only while held/pressed and reverts to off when released. |
| Allowed Touch Direction | dropdown | Which direction a touch must come from to trigger the toggle. 'Front' only accepts touches from the front face; 'Any' accepts touches from all directions. |
| Colorize | dropdown | Which part of the block gets colorized when changing the block color. |
| Hide Body | checkbox | Hides the body of the toggle, leaving only the indicator visible. |

## Related Blocks

- [trigger](/blocks/interfaces/trigger)
- [number](/blocks/interfaces/number)
- [knob_new](/blocks/interfaces/knob_new)
- [toggle](/blocks/interfaces/toggle)

---