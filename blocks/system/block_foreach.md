# Block Foreach

**Category**: ⚙️ System

![block_foreach thumbnail](https://portal.patchxr.io/block-thumbnails/block_foreach.png)

## Description

For each blocks set via the input, it will output the block then its index. Can be use with blocks like set position, set color, to customize blocks given their index.

## Inputs, Outputs and Parts

**Block count**: Output count of blocks when foreach is triggered.

**Input blocks**: 

**Output block**: 

**Trigger**: 

**Index**: Triggered right after the selector output is changed. With its index in the input list starting from 0.

**Interrupt**: Connect the Index output to it, with some logic in between to interrupt the loop, and leave current block in the output. (to select by ID, or with some logic)

---

*Last updated: 2026-01-02 06:30*