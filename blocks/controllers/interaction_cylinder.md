# Interaction Cylinder

**Category**: 🎮 Controllers

![interaction_cylinder thumbnail](https://portal.patchxr.io/block-thumbnails/interaction_cylinder.png)

## Description

A cylindrical interaction volume. Detects when a controller enters it and emits the controller's position in cylindrical coordinates (height, radius, angle), trigger pressure, and roll. Optional haptic feedback per hand.

Like Interaction Box but cylinder-shaped. Subdivide the cylinder with the three 'Num. segments' dials to quantize the position outputs into discrete steps (handy for harp/theremin-style interactions). Each hand has its own set of outputs and a stream input that drives controller vibration. Resize by dragging the small handle at the top.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Left controller haptics | Stream Input | Controls the haptic vibration strength of this hand's controller while inside the cylinder. |
| Left controller haptics | Jolt Input with Dial | Sets the default haptic strength when nothing is driving the stream input. |
| Right controller haptics | Stream Input | Controls the haptic vibration strength of this hand's controller while inside the cylinder. |
| Right controller haptics | Jolt Input with Dial | Sets the default haptic strength when nothing is driving the stream input. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Left controller height | Jolt Output | Vertical position of the left controller, multiplied by the number of height segments. |
| Left controller radius | Jolt Output | The distance of the left controller to the center of the cylinder. |
| Left controller angle | Jolt Output | The angular position of the controller. Range 0 to 1 clockwise. |
| Left controller present | Jolt Output | Sends a 1 when a left controller enters and 0 when it exits. |
| Left controller trigger | Jolt Output | Sends out the analog value of the left controller's trigger button. |
| Left controller roll | Jolt Output | Sends out the roll angle of the left controller. Range -0.5 to 0.5. |
| Right controller present | Jolt Output | Sends 1 when a right controller enters the cylinder and 0 when it exits. |
| Right controller trigger | Jolt Output | Sends out the analog value (0-1) of the right controller's trigger button. |
| Right controller roll | Jolt Output | Sends out the roll angle of the right controller. Range -0.5 to 0.5. |
| Right controller height | Jolt Output | Vertical position of the right controller, multiplied by the number of height segments. |
| Right controller radius | Jolt Output | The distance of the right controller to the center of the cylinder. |
| Right controller angle | Jolt Output | The angular position of the controller. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize handle | Interactible | Grab and drag this corner handle to change the cylinder's height and radius. |
| Num. height segments | Dial | Controls the number of segments along the height of the cylinder. |
| Num. radial segments | Dial | Controls the number of segments going from the middle of the cylinder outwards. |
| Num. angular segments | Dial | Controls the number of segments going around the cylinder (like a clock). |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Interactible when hidden | checkbox | Keeps the cylinder reactive to controllers even when its mesh is hidden. Useful for invisible interaction zones inside a device. |
| Hide Cylinder | checkbox | Hides the cylinder mesh at runtime so the interaction zone becomes invisible. |

## Related Blocks

- [interaction_box](/blocks/controllers/interaction_box)
- [controloutput](/blocks/controllers/controloutput)
- [controllerrotation](/blocks/players/controllerrotation)
- [hapticcontrol](/blocks/players/hapticcontrol)
- [laser_canvas](/blocks/controllers/laser_canvas)

---