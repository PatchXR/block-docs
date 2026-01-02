# Stream Dial

**Category**: 🎚️ Interfaces

![stream_input thumbnail](https://portal.patchxr.io/block-thumbnails/stream_input.png)

## Description

A Stream input/output with interactive dial. Receives, stores, and continiously outputs any received number at sample rate speed (44.1 khz).

Primarily used to pass audio signals.

Blocks with Stream outputs are considered **Stream blocks**. Stream blocks operate at audio sample rate (44.1 khz), making them primarily dedicated for audio generation and manipulation, but are often useful for many other functionality (i.e. driving smooth visualizations).

NOTE: These blocks are heavier on the audio engine then other types of blocks like Jolt blocks which emit discrete values momentarily when triggered. It is advised to use mostly Jolt blocks when possible to optemise CPU usage.

## Inputs, Outputs and Parts

**Stream Out**: Continiously outputs the number from the input/dial, at sample rate.

Grab attach to any other Steam input to connect. 
Click & pull with trigger to create Stream cables.

**Stream Input**: Set the number value to be continiously output from the Stream output.

Primarily used to pass audio signals. Can receive both Stream cables and Jolt wires.
To connect a Stream block here, bring the output of the other block close to this input to snap them together.

---