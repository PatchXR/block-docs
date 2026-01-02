# Envelope

**Category**: 🔊 Audio

![envelope thumbnail](https://portal.patchxr.io/block-thumbnails/envelope.png)

## Description

Generates attack/decay envelopes of various shapes

## Inputs, Outputs and Parts

**Output** *(stream output)*: Outputs the envelope.

**Attack Time** *(stream input)*: How long the attack phase should take.

**Decay Time** *(stream input)*: How long the decay phase should take.

**Trigger Attack/Decay** *(jolt input)*: Trigger an attack followed by a decay.

**Trigger Attack** *(jolt input)*: Trigger an attack, the envelope will stop at the peak.

**Trigger Decay** *(jolt input)*: Trigger a decay, making the envelope go back to zero.

**Attack Done** *(jolt output)*: Sends out a jolt when the attack phase finishes.

**Decay Done** *(jolt output)*: Sounds out a jolt when the decay phase finishes.

---

*Last updated: 2026-01-02 06:20*