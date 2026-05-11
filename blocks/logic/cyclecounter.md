# Counter

**Category**: 🧠 Logic

![cyclecounter thumbnail](https://portal.patchxr.io/block-thumbnails/cyclecounter.png)

## Description

Counts the number of received jolts in a looping manner. Wraps back to zero once the count reaches the set cycle size.

Useful for sequencing, rhythmic patterns, or stepping through indexed elements. The 'On Cycle' output fires every time the counter wraps back to zero.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Cycle size | Stream Input | Sets the value at which the counter will reset and start counting from zero again. |
| Increment | Jolt Input | Counter increment trigger. Each received jolt triggers the count to increase by one. |
| Set | Jolt Input | Sets current count value and triggers the output. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the current count value as a jolt. |
| On Cycle | Jolt Output | Emits a jolt every time the counter wraps back to zero (one full cycle completed). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Counter Display | Button | Displays the current count value. Click to trigger the output and refire the current count. |

## Related Blocks

- counter (link not available)
- [metronome](/blocks/logic/metronome)
- [rangedfor](/blocks/logic/rangedfor)

---