# Device Handle

**Category**: 🎮 Controllers

![device_handle thumbnail](https://portal.patchxr.io/block-thumbnails/device_handle.png)

## Description

Place inside a group/device to turn it into a handheld tool. When a player grabs the device, their controller is hidden and the device snaps into their hand. Jolts report grip, trigger, hand side, A/B buttons and joystick.

Useful for building VR gadgets (wands, guns, lightsabers, instruments) that fully replace the controller in the player's hand. Use the inspector to enable overriding A/B buttons, joystick axes and trigger so they emit on the dedicated outputs instead of triggering their normal Patchworld actions. 'Continuous trigger' makes the trigger output the analog pressure (0-1) instead of a binary 0/1.

## Inputs, Outputs and Parts

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Grip | Jolt Output | Sends out a 1 when you grab the handle and 0 when you let go. |
| Trigger | Jolt Output | Sends out a 1 when you press the trigger while grabbing the handle and 0 when you release. Continuous output can be enabled via the inspector. |
| Hand side | Jolt Output | Sends 0 for right, 1 for left, when the handle is grabbed. |
| Button A Pressed | Jolt Output | Send 1 when A button is pressed, 0 when released. |
| Button B Pressed | Jolt Output | Send 1 when B button is pressed, 0 when released. |
| Thumbstick X | Jolt Output | Output thumbstick horizontal position. -1 is left +1 is right |
| Thumbstick Y | Jolt Output | Output thumbstick vertical position. -1 is down +1 is up |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Continuous trigger | checkbox | When enabled, the Trigger output sends the analog pressure (0-1) every frame. When off, it only sends 1 on press and 0 on release. |
| Hold to grab | checkbox | When enabled, the player must keep grip pressed to hold the device. Otherwise grip toggles holding it (release once to drop it). |
| Use A/X Button | checkbox | When enabled, pressing the A (right) / X (left) button while holding the device emits on the Button A output instead of triggering its normal Patchworld action (radial menu). |
| Use B/Y Button | checkbox | When enabled, pressing the B (right) / Y (left) button while holding the device emits on the Button B output instead of triggering its normal Patchworld action (main menu). |
| Use Joystick X | checkbox | When enabled, horizontal joystick movement emits on the Thumbstick X output instead of turning the player. |
| Use Joystick Y | checkbox | When enabled, vertical joystick movement emits on the Thumbstick Y output instead of thrusting the player. |
| Use Trigger | checkbox | When enabled, the trigger feeds the Trigger output exclusively and stops driving swimming/locomotion while the device is held. |

## Related Blocks

- [device_box](/blocks/visual/device_box)
- [controloutput](/blocks/controllers/controloutput)
- [controllerrotation](/blocks/players/controllerrotation)
- [hapticcontrol](/blocks/players/hapticcontrol)
- [saber](/blocks/controllers/saber)

---