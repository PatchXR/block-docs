---
title: Audio Filters
description: 
published: true
date: 2026-05-11T15:49:51.318Z
tags: filters
editor: markdown
dateCreated: 2026-05-11T15:49:51.318Z
---

# Audio Filters & Effects

This guide covers the Patchworld blocks used to shape, transform, and add space to audio signals: filters, EQ, reverb, delay, pitch shifting, and utility bridges.

---

## Quick Reference

| Block | Thumbnail | What it does |
| :--- | --- | :--- |
| [Filter](/blocks/audio/filter) | ![Filter thumbnail](https://portal.patchxr.io/block-thumbnails/filter.png =60x60) | Biquad LP / HP / BP filter with live display |
| [Eq Band](/blocks/audio/filter_eq) | ![Eq Band thumbnail](https://portal.patchxr.io/block-thumbnails/filter_eq.png =60x60) | Parametric EQ: Low Shelf, High Shelf, or Bell |
| [State Filter](/blocks/audio/statevariable) | ![State Filter thumbnail](https://portal.patchxr.io/block-thumbnails/statevariable.png =60x60) | 10-mode state-variable filter |
| [Delay](/blocks/audio/delay) | ![Delay thumbnail](https://portal.patchxr.io/block-thumbnails/delay.png =60x60) | Audio delay line (modulatable at audio rate) |
| [Reverb](/blocks/audio/reverb) | ![Reverb thumbnail](https://portal.patchxr.io/block-thumbnails/reverb.png =60x60) | FDN / Tank / Freeverb reverb |
| [Pitch Shifter](/blocks/audio/pitchshifter) | ![Pitch Shifter thumbnail](https://portal.patchxr.io/block-thumbnails/pitchshifter.png =60x60) | Real-time pitch shift in semitones |
| [Sample And Hold](/blocks/audio/sample_and_hold) | ![Sample And Hold thumbnail](https://portal.patchxr.io/block-thumbnails/sample_and_hold.png =60x60) | Freeze a signal value on a trigger |
| [Stoe](/blocks/connectors/stoe) | ![Stoe thumbnail](https://portal.patchxr.io/block-thumbnails/stoe.png =60x60) | Convert stream → jolt (bridge to logic blocks) |
| [Watcher](/blocks/logic/watcher) | ![Watcher thumbnail](https://portal.patchxr.io/block-thumbnails/watcher.png =60x60) | Fire a jolt when a stream condition becomes true |

---

## Filter

![Filter thumbnail](https://portal.patchxr.io/block-thumbnails/filter.png =80x80)

[Filter](/blocks/audio/filter) is a **biquad filter** — the go-to choice for classic electronic music filtering. It has a live frequency-response graph on its face.

**Three modes** (select via dial, serialized as `tp`):

| Mode | Effect |
| :--- | :--- |
| **LP** (Low-Pass, `tp:0`) | Lets bass through, cuts highs. Warm, dark sound. |
| **HP** (High-Pass, `tp:1`) | Lets highs through, cuts bass. Thin, crisp sound. |
| **BP** (Band-Pass, `tp:2`) | Narrow band only. Telephone / radio effect. |

**Resonance** (`k_rs`): adds a peak at the cutoff. Sweep cutoff + resonance together for the classic filter sweep.

```
[ Oscillator ] --> [ Filter ] --> [ Speaker ]
                      ^
              [ LFO (Oscillator) ] --> stream input: Cutoff Frequency
```

---

## Eq Band

![Eq Band thumbnail](https://portal.patchxr.io/block-thumbnails/filter_eq.png =80x80)

[Eq Band](/blocks/audio/filter_eq) is a **parametric EQ** that can boost *or* cut, unlike the plain Filter which only cuts. It also has a live display.

**Three shapes** (serialized as `tp`):

| Shape | Effect |
| :--- | :--- |
| **Low Shelf** (`tp:0`) | Boosts/cuts all frequencies below the cutoff. |
| **High Shelf** (`tp:1`) | Boosts/cuts all frequencies above the cutoff. |
| **Bell** (`tp:2`) | Boosts/cuts a band centered on the cutoff. |

**Gain**: > 1.0 = boost, < 1.0 = cut, 1.0 = no effect.  
**Steepness** (`k_st`): narrows the affected band (useful with Bell).

> [!TIP]
> Chain multiple Eq Band blocks in series to build a multi-band equalizer.

---

## State Filter

![State Filter thumbnail](https://portal.patchxr.io/block-thumbnails/statevariable.png =80x80)

[State Filter](/blocks/audio/statevariable) is a more flexible filter with **10 modes** in a single block. All modes are computed simultaneously at audio rate — switching modes (via the dial or `joltInput[3]`) is instantaneous and click-free.

| Mode | Code | Description |
| :--- | :--- | :--- |
| High-Pass | `tp:0` | Cuts bass |
| Band-Pass | `tp:1` | Narrow band |
| Low-Pass | `tp:2` | Cuts highs |
| Unity-Gain BP | `tp:3` | Band-pass at constant amplitude |
| Notch | `tp:4` | Cuts a narrow band |
| All-Pass | `tp:5` | Flat amplitude, rotates phase |
| Peak | `tp:6` | Boosts/cuts a narrow band |
| Low Shelf | `tp:7` | Boosts/cuts below cutoff |
| Band Shelf | `tp:8` | Boosts/cuts a band |
| High Shelf | `tp:9` | Boosts/cuts above cutoff |

> [!NOTE]
> The Cutoff Frequency must be ≥ 1 Hz. Feeding it 0 will cause the filter to malfunction.

---

## Delay

![Delay thumbnail](https://portal.patchxr.io/block-thumbnails/delay.png =80x80)

[Delay](/blocks/audio/delay) is a **pure audio-rate delay line**. The delay time is modulated at audio rate, enabling:

- **Echo**: long delay times (0.1 s – 2 s+) with feedback loop.
- **Chorus / Flanger**: very short times (< 30 ms) modulated by an LFO.
- **Comb filtering**: very short static times create resonant peaks.

**Feedback loop** (delay → speaker with echo):
```
[ Oscillator ] --+------> [ Delay ] ---------> [ Speaker ]
                 |           |
                 +-- Delay Input <-- delay time set by knob
```

**Chorus** (modulated short delay):
```
[ Microphone ] --> [ Delay ] --> [ Speaker ]
                       ^
          [ Oscillator 0.5–2 Hz, 0.005–0.02 s range ] --> Delay Time
```

---

## Reverb

![Reverb thumbnail](https://portal.patchxr.io/block-thumbnails/reverb.png =80x80)

[Reverb](/blocks/audio/reverb) simulates acoustic space. Three algorithms, switchable at runtime:

| Algorithm | `tp` | Character |
| :--- | :--- | :--- |
| **FDN** | `tp:0` | Clean digital hall — smooth and modern |
| **Tank** | `tp:1` | Vintage spring reverb — warm and wobbly |
| **Freeverb** | `tp:2` | Classic plate reverb |

**Key controls**:
- **Decay Time** (s): room size / tail length.
- **Absorption** (0–1): high-frequency damping. Low = bright/reflective, High = dark/muffled.
- **Mix** (0–1): dry/wet balance.

> [!TIP]
> Use Mix at 0.2–0.4 for a subtle room feel. Use Mix > 0.8 for long ambient pads.

---

## Pitch Shifter

![Pitch Shifter thumbnail](https://portal.patchxr.io/block-thumbnails/pitchshifter.png =80x80)

[Pitch Shifter](/blocks/audio/pitchshifter) shifts the pitch of an audio signal in **semitones** in real time.

| Semitones | Effect |
| :--- | :--- |
| 0 | No shift |
| 12 | One octave up |
| -12 | One octave down |
| 7 | Perfect fifth up |

Since the shift is a stream input, it can be modulated by an LFO for **vibrato**, or driven from a controller for live pitch-bend.

```
[ Microphone ] --> [ Pitch Shifter ] --> [ Speaker ]
                          ^
               [ Map Stream: joystick Y → -12 to 12 ]
```

---

## Sample And Hold

![Sample And Hold thumbnail](https://portal.patchxr.io/block-thumbnails/sample_and_hold.png =80x80)

[Sample And Hold](/blocks/audio/sample_and_hold) **freezes** a stream value the moment a trigger fires, and holds it until the next trigger. Classic modular synthesis utility.

**Two trigger methods**:
- **Clock (stream)**: triggered on each rising edge of the clock stream (connect a square-wave LFO or a Metronome → Stoe).
- **Sample (jolt)**: triggered by any jolt event.

**Classic random melody generator**:
```
[ Noise ] --> [ Sample And Hold ] --> [ Map Stream: min-max ] --> [ Oscillator frequency ]
                     ^
             [ Metronome ] --> [ Stoe ] --> Sample (jolt)
```

---

## Stoe (Stream → Jolt Bridge)

![Stoe thumbnail](https://portal.patchxr.io/block-thumbnails/stoe.png =80x80)

[Stoe](/blocks/connectors/stoe) (**S**tream **T**o **E**vent) converts a continuous stream into jolt events capped at ~90 Hz.

Use it when you need to feed a stream value into a logic block that only accepts jolts (e.g., [Map Jolt](/blocks/logic/map_jolt), [Gate](/blocks/logic/gate), [Compare](/blocks/logic/compare)).

---

## Watcher (Threshold Detection)

![Watcher thumbnail](https://portal.patchxr.io/block-thumbnails/watcher.png =80x80)

[Watcher](/blocks/logic/watcher) compares two stream values at audio rate using a chosen operator (=, ≠, >, ≥, <, ≤, AND, OR, XOR).

- **Jolt Output**: fires once when the condition becomes true (rising edge).
- **Stream Output 0/1**: continuously 1 while the condition is true, 0 while false.

This is more efficient than Stoe → Compare for threshold detection because no intermediate jolt flood is produced.

**Example: trigger an event when a filter is fully open**
```
[ LFO ] --> [ Filter Cutoff Freq ]
        |
        +--> [ Watcher Signal A ]
                [ Watcher Signal B ] <-- constant 18000 (Hz)
                [ Watcher Operator ] = ">="
                [ Watcher Jolt Out ] --> [ any event ]
```

---

## Cheat Sheet: Signal Chain Examples

| Goal | Blocks |
| :--- | :--- |
| Classic synth filter sweep | [Oscillator](/blocks/audio/oscillator) → [Filter](/blocks/audio/filter) → [Speaker](/blocks/audio/output) |
| Multi-band EQ | [Eq Band](/blocks/audio/filter_eq) (Low Shelf) → [Eq Band](/blocks/audio/filter_eq) (Bell) → [Eq Band](/blocks/audio/filter_eq) (High Shelf) |
| Room reverb | [Speaker input] → [Reverb](/blocks/audio/reverb) (Mix 0.3) → [Speaker](/blocks/audio/output) |
| Echo with feedback | [Delay](/blocks/audio/delay) with output fed back to input via stream fork |
| Chorus | [Delay](/blocks/audio/delay) with slow LFO on Delay Time (5–20 ms range) |
| Pitch harmonizer | [Pitch Shifter](/blocks/audio/pitchshifter) (+7 semitones) mixed with dry signal |
| Random pitch sequencer | [Noise](/blocks/audio/noise) → [Sample And Hold](/blocks/audio/sample_and_hold) → [Oscillator](/blocks/audio/oscillator) frequency |
| Trigger when signal exceeds threshold | [Watcher](/blocks/logic/watcher) (operator ≥, Signal B = threshold) → jolt |
| Feed a stream value into a jolt-only block | [Stoe](/blocks/connectors/stoe) → any jolt input |
