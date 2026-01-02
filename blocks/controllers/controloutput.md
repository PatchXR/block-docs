# Controller Output

**Category**: 🎮 Controllers

![controloutput thumbnail](https://portal.patchxr.io/block-thumbnails/controloutput.png)

## Description

Outputs various data from the controllers (grip/trigger/buttons/joystick...)

## Inputs, Outputs and Parts

**Trigger Right** *(jolt output)*: Emits values between 0-1 when right controller's trigger is squeezed

**Grip Right** *(jolt output)*: Emits values between 0-1 when right controller's grip is squeezed

**Button A Right** *(jolt output)*: Emits 1 when A button on the right controller is pressed

**Button B Right** *(jolt output)*: Emits 1 when B button on the right controller is pressed

**Head Distance** *(jolt output)*: Emits distance between the head and the controller

**Trigger Left** *(jolt output)*: Emits values between 0-1 when left controller's trigger is squeezed

**Grip Left** *(jolt output)*: Emits values between 0-1 when left controller's grip is squeezed

**Button A Left** *(jolt output)*: Emits 1 when A button on the left controller is pressed

**Button B Left** *(jolt output)*: Emits 1 when B button on the left controller is pressed

**Distance Between Controllers** *(jolt output)*: Emits distance between the controllers

**Input Player**: Restrict to a specific player.
- No connection: use local player
- Connection to player: restrict to player
- Connection to controller: both sides output the same controller state

## Related Blocks

- [controllerrotation](/blocks/players/controllerrotation)
- [controllerposition](/blocks/players/controllerposition)
- [moveanalysis](/blocks/controllers/moveanalysis)
- [hapticcontrol](/blocks/players/hapticcontrol)

---