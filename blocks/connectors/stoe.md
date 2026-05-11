# Stoe

**Category**: 🔗 Connectors

![stoe thumbnail](https://portal.patchxr.io/block-thumbnails/stoe.png)

## Description

Converts a stream signal into jolt events. Emits the current stream value as a jolt each time the stream changes (at most 90 times per second).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| input | Stream Input | The stream to convert. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| output | Jolt Output | Emits the value of the incoming stream as a jolt. |

## Related Blocks

- [watcher](/blocks/logic/watcher)

---