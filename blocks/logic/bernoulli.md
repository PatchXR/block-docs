# Bernoulli

**Category**: 🧠 Logic

![bernoulli thumbnail](https://portal.patchxr.io/block-thumbnails/bernoulli.png)

## Description

Routes an incoming jolt to either of two outputs based on probability. With probability set closer to 0 the jolt is more likely to go through output A, while if set closer to 1 it's more likely to go through output B.

Useful for randomized branching in patches: probabilistic event routing, weighted choices, or stochastic gameplay logic.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Probability | Stream Input | Probability distribution value. |
| Input | Jolt Input | Receives jolt value which will be passed to either of the outputs. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output A | Jolt Output | Emits the received jolt when probability rolls below the threshold (more likely when probability is closer to 0). |
| Output B | Jolt Output | Emits the received jolt when probability rolls above the threshold (more likely when probability is closer to 1). |

## Related Blocks

- [random](/blocks/logic/random)
- sequence_random (link not available)
- [route](/blocks/logic/route)

---