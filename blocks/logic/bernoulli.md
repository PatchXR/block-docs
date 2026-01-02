---
title: Bernoulli
description: Documentation for Bernoulli block
published: true
date: 2026-01-02T01:53:16.760Z
tags: blocks, logic
editor: markdown
dateCreated: 2026-01-02T01:53:16.760Z
---

# bernoulli

**Category**: Logic

![bernoulli thumbnail](https://portal.patchxr.io/block-thumbnails/bernoulli.png)

## Description

Routes an incoming jolt to either of two outputs based on probability. With probability value set closer to 0 the jolt will more like go though output A, while if value will be set closer to 1 - though output B.

## Inputs, Outputs and Parts

**Probability** *(stream input)*: Probability distribution value.

**Output A** *(jolt output)*: Emits jolt value based on set probability.

**Output B** *(jolt output)*: Emits jolt value based on set probability.

**Input** *(jolt input)*: Receives jolt value which will be passed to either of the outputs.

## Related Blocks

- [random](/blocks/random)
- [sequence_random](/blocks/sequence_random)

---

*Auto-generated from block documentation*