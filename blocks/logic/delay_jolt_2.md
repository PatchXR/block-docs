# Delay Jolt

**Category**: 🧠 Logic

![delay_jolt_2 thumbnail](https://portal.patchxr.io/block-thumbnails/delay_jolt_2.png)

## Description

Delays incoming jolts by a specified time period with configurable behavior for overlapping jolts.

Adds time delay to jolt signals with two behavior modes: Queued (all jolts are delayed and output in order) or Last (only the most recent jolt is delayed, canceling previous ones). Useful for timing control and preventing rapid-fire triggers.

## Inputs, Outputs and Parts

**Delay** *(stream input)*: Time delay in seconds before jolts are output

**Jolt In** *(jolt input)*: Input jolts to be delayed

**Jolt Out** *(jolt output)*: Delayed jolt output (behavior depends on mode setting)

## Related Blocks

- [delay](/blocks/audio/delay)
- [metronome](/blocks/logic/metronome)
- [gate](/blocks/logic/gate)

---