# Set Dsp Enabled

**Category**: ⚙️ System

![set_dsp_enabled thumbnail](https://portal.patchxr.io/block-thumbnails/set_dsp_enabled.png)

## Description

Turn audio DSP processing on or off for selected blocks/groups. Use it to free CPU on parts of the patch that aren't audible right now.

Connect any audio blocks (or whole groups/devices via subpatch) to the Tag input, then toggle DSP via the on-block switch or the jolt input. Disabled blocks stop spending audio thread cycles, which is the cheapest way to reclaim performance in big patches - turn off the synth in room A while the player is in room B.

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Target blocks | Tag Input | Tag input. Connect any audio blocks (or whole groups/devices) you want to enable/disable. |
| DSP Enable | Jolt Input | Send any non-zero value to enable DSP on the connected blocks; send 0 to disable. |

## Related Blocks

- [set_active](/blocks/system/set_active)
- [set_visible](/blocks/system/set_visible)
- [set_interactive](/blocks/system/set_interactive)
- [set_lock](/blocks/system/set_lock)
- [block_list](/blocks/system/block_list)

---