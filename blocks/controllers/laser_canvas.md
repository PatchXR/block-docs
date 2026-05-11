# Laser Canvas

**Category**: 🎮 Controllers

![laser_canvas thumbnail](https://portal.patchxr.io/block-thumbnails/laser_canvas.png)

## Description

A canvas that lets you control things with the laser pointer.

When you point your controller at the canvas it will activate the laser pointer (like e.g. in the hub). Jolt outputs let you get the controller state.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Active | Jolt Input | Send a 1 to activate the laser, send a 0 to deactivate it. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| x | Jolt Output | Emits the normalized (0 to 1) x coordinate of where you're pointing on the canvas. |
| y | Jolt Output | Emits the normalized (0 to 1) y coordinate of where you're pointing on the canvas. |
| hover | Jolt Output | Emits a 1 when you start pointing at the canvas and 0 when you stop. |
| trigger | Jolt Output | Emits a 1 when you press the trigger while pointing at the canvas, and 0 when you stop or exit the canvas. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize | Draggable part | Move with trigger to resize the canvas. |
| Canvas | Interactible | Point your controller at the canvas to interact with it. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Distance limit | text_input | Maximum distance from which the laser can target the canvas, in meters. |
| Execute for local player only | toggle | When enabled, this canvas only fires its jolt outputs for the local player and not for other players in the session. |
| Lock Size | checkbox | When enabled, the resize handle is disabled and the canvas size cannot be changed. |

## Related Blocks

- [interaction_box](/blocks/controllers/interaction_box)
- [controloutput](/blocks/controllers/controloutput)
- [controllerrotation](/blocks/players/controllerrotation)

---