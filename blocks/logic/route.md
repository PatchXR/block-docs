# Route

**Category**: 🧠 Logic

![route thumbnail](https://portal.patchxr.io/block-thumbnails/route.png)

## Description

Routes an incoming jolt to one or several outputs using a selectable behavior: by index, looped (one after another), random, or all at once.

Drag the handle to resize the number of outputs. Behaviors:
- Index: send to the output matching the stream value.
- Loop: cycle through outputs sequentially on each jolt.
- Random: pick one output at random.
- All: emit on every output simultaneously.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Input | Jolt Input | Send your value here. |
| Reset | Jolt Input | Reset the index to zero. (loop mode) |
| Index | Stream Input | Will select which output will be triggered. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Route Type | Selector | Selects the routing behavior. Index: sends to the output matching the stream value. Loop: cycles through outputs one by one. Random: picks one at random. All: fires every output. |
| Resize | Draggable part | Drag to change the number of output emitters. |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Lock Size | checkbox | When enabled, prevents the number of outputs from being changed by dragging the resize handle. |

## Related Blocks

- [route_reverse](/blocks/logic/route_reverse)
- [reverse_route_stream](/blocks/audio/reverse_route_stream)
- [fork](/blocks/connectors/fork)
- [gate](/blocks/logic/gate)

---