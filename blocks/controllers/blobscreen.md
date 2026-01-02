# Blobscreen

**Category**: 🎮 Controllers

![blobscreen thumbnail](https://portal.patchxr.io/block-thumbnails/blobscreen.png)

## Inputs, Outputs and Parts

**resize** *(interactive)*: Grab to change the size of the touch screen

**blobs** *(interactive)*: Grab and drag to change the number of blobs..

**num_columns** *(knob)*: Change the number of columns shown on the display.

**num_rows** *(knob)*: Change the number of columns shown on the display.

**fuzz**: Sets the amount of fuzz on the blobs.

**position_x** *(jolt input)*: Sets the X position of the blob.

**position_y** *(jolt input)*: Sets the y position of the blob.

**position_z** *(jolt input)*: Sets the z position of the blob.

**enabled** *(jolt input)*: Send a 1 to enable the blob, 0 to disable..

**pulse** *(jolt input)*: Send a jolt to make the blob bounce.

**pulse** *(jolt input)*: Send a jolt to make the blob bounce.

**amp** *(jolt input)*: Sets the intensity of the blob.

**character** *(jolt input)*: Sets the character of the blob.

**blob** *(jolt input)*: No sure what this one does.

**loop** *(jolt input)*: Send 1 to enable looping, 0 to disable.

**loop_select** *(jolt input)*: Send jolts with different values to create and recall multiple loops.

**loop_length** *(jolt input)*: Sets the length of the current loop in beats.

**position_x** *(jolt output)*: Emits the x position of the blob.

**position_y** *(jolt output)*: Emits the y position of the blob.

**position_z** *(jolt output)*: Emits the z position of the blob.

**touch** *(jolt output)*: Emits a jolt when you touch the blob.

**trigger** *(jolt output)*: Emits how far down the pistol trigger is pressed while grabbing the blob.

**cross** *(jolt output)*: Emits a jolt whenever a blob crosses between to columns.

**enabled** *(jolt output)*: Emits 1 when the blobs is enabled and 0 when disabled.

**loop progress** *(jolt output)*: Emits a value between 0 and 1 indicating how far along this blob is in its loop.

---

*Last updated: 2026-01-02 06:27*