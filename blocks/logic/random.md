# Random

**Category**: 🧠 Logic

![random thumbnail](https://portal.patchxr.io/block-thumbnails/random.png)

## Description

Outputs a random decimal number between 0 and <b>Max</b> each time it is triggered.

Trigger by clicking the button or sending a jolt to the Trigger Random input. The Max value (set via the dial or the stream input) defines the upper bound of the random range. Useful for randomized melodies, dice rolls, scattered spawn positions, or any time you need variation.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Trigger Random | Jolt Input | Send a jolt to generate a new random value. The current Max input determines the range. |
| Max Value | Stream Input | Upper bound of the random range. The output will be between 0 and this value. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the newly generated random value as a jolt. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Trigger | Interactible | Displays the current Max value. Click to roll a new random number. |

## Related Blocks

- [bernoulli](/blocks/logic/bernoulli)
- [noise](/blocks/audio/noise)
- [rangedfor](/blocks/logic/rangedfor)
- [operation](/blocks/logic/operation)
- [metronome](/blocks/logic/metronome)

---