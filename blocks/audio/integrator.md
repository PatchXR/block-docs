# integrator

**Category**: 🔊 Audio

![integrator thumbnail](https://portal.patchxr.io/block-thumbnails/integrator.png)

## Description

A leaky integrator with separate constants for the rise and fall time. This block can be used to smooth out an incoming signal so that the change in the signal level cannot exceed a certain value per second. Combine with the 'abs' block to create an envelope follower.

## Inputs, Outputs and Parts

**Signal input** *(stream input)*: The signal to integrate.

**Rise control** *(stream input)*: The integration constant to use when the signal is rising.

**Fall control** *(stream input)*:  The integration constant to use when the signal is falling.

**Set value** *(jolt input)*: Immediately set the internal value of the integrator. Usually you will want to set the value of the signal (stream) input as well.

---

*Last updated: 2026-01-02 06:02*