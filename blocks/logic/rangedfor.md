# Rangedfor

**Category**: 🧠 Logic

![rangedfor thumbnail](https://portal.patchxr.io/block-thumbnails/rangedfor.png)

## Description

Instantly sends N jolts, from 0 to N-1, when triggered. Useful for iterating over a fixed range of indices.

Each trigger pulse causes N sequential jolts to fire in rapid succession. Combine with a route or compare block to perform per-index actions, like spawning N copies or seeding indexed parameters.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Trigger | Jolt Input | Triggers the process of sending jolts from 0 to N-1 (where N is set by the received jolt value). |
| Range | Stream Input | Sets N, the number of jolts to output when triggered. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output | Jolt Output | Emits jolts from zero to N-1. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Trigger | Interactible | Click to trigger manually. |

## Related Blocks

- nth (link not available)
- [cyclecounter](/blocks/logic/cyclecounter)
- [metronome](/blocks/logic/metronome)
- [route](/blocks/logic/route)

---