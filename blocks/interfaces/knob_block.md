# Jolt Dial

**Category**: 🎚️ Interfaces

![knob_block thumbnail](https://portal.patchxr.io/block-thumbnails/knob_block.png)

## Description

Jolt input with a dial around it. Sets and instantly triggers any number changes from the Jolt output.


Useful as a user interface in patches and devices where wide range of various numbers are expected. And as an interface with a primary input in the front for accessible patching.

To change the number there are 2 interaction methods that allow you to easily input any number:
1. Click on the number and drag up or down to change the selected number, to change decimal, click on another decimal point on the 3D interface that pops up, and drag up or down.
2. Use joystick up/down to change number of currently selected digit, and left/right to move up or down the decimal digit points.

Check inspector for more settings.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Knob | Jolt Input with Dial | Changing and emitting the number can be done by click & drag up/down to input any number, joystick up/dow/left/right, or, connecting and sending any number from the jolt input in the front.  To connect another block here, click & pull on any Jolt output to create a wire and drag it here. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Jolt Out | Jolt Output | Emits the newly changed number when number is changed.  Click & pull to generate a new Jolt wire. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Allow Decimals | checkbox | When enabled, allows the dial to be set to decimal (non-integer) values. |
| Set Minimum | checkbox | When enabled, restricts the dial to a minimum value. Turn the knob to the desired minimum after enabling. |
| Set Maximum | checkbox | When enabled, restricts the dial to a maximum value. Turn the knob to the desired maximum after enabling. |

---