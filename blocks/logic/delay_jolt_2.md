# Delay Jolt

**Category**: 🧠 Logic

![delay_jolt_2 thumbnail](https://portal.patchxr.io/block-thumbnails/delay_jolt_2.png)

## Description

Delays incoming jolts by a specified time, with configurable behavior for handling overlapping jolts.

Adds a time delay to jolt signals with two behavior modes (set in the inspector):
- Queued: every incoming jolt is delayed and replayed in order.
- Last: only the most recent jolt is held; any new jolt cancels the pending one and restarts the timer. A progress stream output (0 to 1) is exposed in this mode.
Useful for timing control, debouncing rapid triggers, or building sequenced cascades.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Delay | Stream Input | Time delay in seconds before jolts are output. |
| Jolt to delay | Jolt Input | Incoming jolt to be delayed. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Jolt Out | Jolt Output | Emits the delayed jolt (behavior depends on the inspector Behavior setting). |
| Progress 0-1 | Stream Output | Ramps from 0 to 1 over the pending delay period (only active in 'Last' behavior mode). |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Behavior | dropdown | Queued: every incoming jolt is delayed and replayed in order. Last: only the most recent jolt is held; new jolts cancel the pending one and restart the timer (Progress 0-1 output is enabled in this mode). |

## Related Blocks

- [delay](/blocks/audio/delay)
- [metronome](/blocks/logic/metronome)
- [gate](/blocks/logic/gate)
- [pass](/blocks/connectors/pass)
- [cyclecounter](/blocks/logic/cyclecounter)

---