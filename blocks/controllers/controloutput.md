# Controller Output

**Category**: 🎮 Controllers

![controloutput thumbnail](https://portal.patchxr.io/block-thumbnails/controloutput.png)

## Description

Outputs various data from both controllers: grip, trigger, buttons, joystick axes, head distance, and distance between controllers.

## Related Wiki Pages

[player-inputs](/patching/player-inputs)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input Player | Tag Input | Restrict to a specific player. - No connection: use local player - Connection to player: restrict to player - Connection to controller: both sides output the same controller state |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Trigger Right | Jolt Output | Emits values between 0-1 when right controller's trigger is squeezed |
| Grip Right | Jolt Output | Emits values between 0-1 when right controller's grip is squeezed |
| Button A Right | Jolt Output | Emits 1 when A button on the right controller is pressed |
| Button B Right | Jolt Output | Emits 1 when B button on the right controller is pressed |
| Trigger Left | Jolt Output | Emits values between 0-1 when left controller's trigger is squeezed |
| Grip Left | Jolt Output | Emits values between 0-1 when left controller's grip is squeezed |
| Button A Left | Jolt Output | Emits 1 when A button on the left controller is pressed |
| Button B Left | Jolt Output | Emits 1 when B button on the left controller is pressed |
| Distance Between Controllers | Jolt Output | Emits distance between the controllers |
| Right Joy X axis | Jolt Output |  |
| Right Joy Y axis | Jolt Output |  |
| Right Joy Pressed | Jolt Output |  |
| Head Distance Right | Jolt Output | Distance from the right controller to your head. |
| Head Distance Left | Jolt Output | Distance from the left controller to your head. |
| Left Joy X axis | Jolt Output |  |
| Left Joy Y axis | Jolt Output |  |
| Left Joy Pressed | Jolt Output |  |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Uses Right Button A | checkbox | When enabled, this block claims priority use of the A button, preventing the radial menu or other blocks from consuming it. |
| Uses Right Button B | checkbox | When enabled, this block claims priority use of the B button, preventing the main menu or other blocks from consuming it. |
| Uses Right Trigger | checkbox | When enabled, this block claims priority use of the trigger, preventing other interaction systems from consuming it. |
| Uses Right Joystick X | checkbox | When enabled, this block claims priority use of the joystick horizontal axis, preventing locomotion or other blocks from consuming it. |
| Uses Right Joystick Y | checkbox | When enabled, this block claims priority use of the joystick vertical axis, preventing locomotion or other blocks from consuming it. |
| Uses Right Joystick Click | checkbox | When enabled, this block claims priority use of the joystick click, preventing other blocks from consuming it. |

## Related Blocks

- [controllerrotation](/blocks/players/controllerrotation)
- [controllerposition](/blocks/players/controllerposition)
- [moveanalysis](/blocks/controllers/moveanalysis)
- [hapticcontrol](/blocks/players/hapticcontrol)

---