# Block List

**Category**: ⚙️ System

![block_list thumbnail](https://portal.patchxr.io/block-thumbnails/block_list.png)

## Description

A searchable list of every block in the current world. Hover an item to open its radial menu so you can remove, inspect, lock or teleport to that block.

Useful in big patches to find a specific block, audit content, or monitor CPU usage per block (via the 'CPU Profiling Mode' inspector setting). Can also be opened on demand with the 'ShowBlockList' console command. Type in the search field to filter, and click an entry to act on the matching block.

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| CPU Profiling Mode | dropdown | Controls how CPU usage is measured and displayed next to each block. 'Off' = no profiling. 'All' = profile every block while the list is open. 'OnHover' = profile only the block currently hovered in the list. |

## Related Blocks

- [block_watcher](/blocks/system/block_watcher)
- [scene_watcher](/blocks/system/scene_watcher)
- [block_foreach](/blocks/system/block_foreach)

---