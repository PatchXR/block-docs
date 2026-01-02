# laser_canvas

**Category**: 🎮 Controllers

![laser_canvas thumbnail](https://portal.patchxr.io/block-thumbnails/laser_canvas.png)

## Description

A canvas that lets you control stuff with the laser pointer.

When you point your controller at the canvas it will activate the laser pointer (like e.g. in the hub). Jolt outputs lets you get the controller state.

## Inputs, Outputs and Parts

**Resize** *(interactive)*: Move with trigger to resize the canvas.

**Canvas** *(interactive)*: Point your controller at the canvas to interact with it.

**Active** *(jolt input)*: Send a 1 to activate the laser, send a 0 to deactivate it.

**x** *(jolt output)*: Emits the normalized (0 to 1) x coordinate of where you're pointing at the canvas.

**y** *(jolt output)*: Emits the normalized (0 to 1) y coordinate of where you're pointing at the canvas.

**hover** *(jolt output)*: Emits a 1 when you start pointing at the canvas and 0 when you stop.

**trigger**: Emits a 1 when you press the trigger while pointing at the canvas, and 0 when you stop or exit the canvas.

---

*Last updated: 2026-01-02 05:54*