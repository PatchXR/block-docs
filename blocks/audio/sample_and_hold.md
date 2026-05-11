# Sample And Hold

**Category**: 🔊 Audio

![sample_and_hold thumbnail](https://portal.patchxr.io/block-thumbnails/sample_and_hold.png)

## Description

Captures and holds the value of a signal when triggered by a clock signal or jolt.

## Related Wiki Pages

[audio-filters](/patching/audio-filters)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Clock input | Stream Input | Each time this value goes high, the current signal input value is captured and held. |
| Signal input | Stream Input | Signal to be sampled. |
| Sample | Jolt Input | Send a jolt to immediately capture and hold the current signal input value. |

## Related Blocks

- [watcher](/blocks/logic/watcher)

---