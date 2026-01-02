# limiter

**Category**: Experimental

![limiter thumbnail](https://portal.patchxr.io/block-thumbnails/limiter.png)

## Description

Applies brick wall limiting to the incoming signal, to control the amplitude.

## Inputs, Outputs and Parts

**Signal input** *(stream input)*: The signal to which the limiting will be applied.

**Release time** *(stream input)*: How fast the limiter will stop suppressing the input signal once the threshold is no longer crossed.

**Look-ahead time** *(stream input)*: Time 'ahead' at which the limiter will start suppressing the signal once the threshold has been crossed.

**Attack time** *(stream input)*: How fast the limiter will start suppressing the input signal once the threshold level has been crossed.

**Threshold level** *(stream input)*: The signal level above which the limiting will be applied. Set in linear units. (0-1 range)

## Tags

To Refurbish

---

*Last updated: 2026-01-02 04:53*