# Funnel Jolt

**Category**: 🧠 Logic

![route_reverse thumbnail](https://portal.patchxr.io/block-thumbnails/route_reverse.png)

## Description

Combines N jolt inputs into a single output. Either filters incoming jolts by an index (Select Gate mode), or emits the index of whichever input fired (Output Index mode).

Drag the handle to resize the number of inputs. Behaviors:
- Select Gate: only the input matching the index value passes through.
- Output Index: every input passes through, but the output value is the index of the input that fired (useful to know which one triggered).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Index | Stream Input | Selects which input is allowed to pass through (only used in Select Gate mode). |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits the jolt forwarded from one of the inputs (the value depends on the selected behavior). |

### Others

| Name | Type | Description |
|------|------|-------------|
| Behavior | Selector | Sets the funnel behavior. Select Gate: only the input matching the index value is forwarded. Output Index: any input fires the output with its own index as the value. |
| Resize | Draggable part | Drag to change the number of jolt inputs. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Lock Size | checkbox | When enabled, prevents the number of inputs from being changed by dragging the resize handle. |

## Related Blocks

- [route](/blocks/logic/route)
- [reverse_route_stream](/blocks/audio/reverse_route_stream)
- [fork](/blocks/connectors/fork)
- [gate](/blocks/logic/gate)

---