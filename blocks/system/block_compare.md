# Block Compare

**Category**: ⚙️ System

![block_compare thumbnail](https://portal.patchxr.io/block-thumbnails/block_compare.png)

## Description

Combines two lists of blocks (A, B) into a third list using a configurable Behavior (set operations, picking, navigation up/down the hierarchy, grabbing detection, etc.). Output Count fires after every recompute and is also the easiest way to watch when A or B changes.

Block Compare is the swiss-army knife of dynamic patching: it takes one or two block lists in input and produces a derived list in output following the selected Behavior. The block re-evaluates automatically whenever A, B or Behavior change; connect a jolt to the Manual Trigger to control execution explicitly. Output Count emits the size of the result list and re-fires every time the list changes (useful as a "watcher" on dynamic inputs).

Use cases: trimming a [raycast](/blocks/controllers/raycast) result, finding which blocks were added or removed since last frame, walking up to the parent Device of a block, finding the player who grabbed an object, or storing a list of references that survives input changes.

**Behavior options:**

- **==** : outputs A only when A and B contain the exact same blocks (Output Count is 1 if equal, 0 otherwise). Great for "all targets hit" gates.
- **A-B** : outputs every block of A that is *not* in B. Use it to track what was added (`current - previous`) or to filter blocks out (e.g. all enemies *except* the boss).
- **Shared** : outputs only the blocks that appear in **both** A and B (set intersection). Handy to detect overlap between two dynamic lists.
- **Join** : outputs the union of A and B with duplicates removed.
- **Last** : outputs only the last block of A (the most recently connected). The B input is hidden.
- **First** : outputs only the first block of A.
- **Device** : outputs the parent Device of each block in A (or the block itself if it isn't inside a Device). Useful to escalate a per-part match to the Device that owns it.
- **Parent** : outputs the parent Group/Device main part of each block in A. Returns nothing for top-level blocks.
- **Grabber** : outputs the controller(s) currently grabbing each block in A. Combined with Manual Trigger, this is the cleanest way to know *who* is interacting with a block.
- **Store** : keeps every block ever connected to A and accumulates them in the output. The internal store is cleared by the Clear jolt. Perfect to maintain a persistent set as A flickers.
- **Index** : the Manual Trigger jolt value is used as an index into A; the block at that index is output. Combine with [block_foreach](/blocks/system/block_foreach) or a counter to read items by position.

The **B** input only appears for behaviors that need it (==, A-B, Shared, Join). For all others, B is hidden and any connections to it are dropped.

See the [Dynamic Patching](/wiki/dynamic-patching) wiki page for full examples.

## Related Wiki Pages

[dynamic-patching](/patching/dynamic-patching)

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| A | Tag Input | Primary list of blocks. Most behaviors only consider A (Last, First, Device, Parent, Grabber, Store, Index). |
| B | Tag Input | Secondary list of blocks. Only visible and used by the set-style behaviors: ==, A-B, Shared and Join. |
| Manual Trigger | Jolt Input | If connected: only re-evaluates when this jolt fires. Its value is also used as the index when Behavior is set to "Index". If not connected: re-evaluates automatically whenever A or B change. |
| Clear | Jolt Input | Empties the Output. Mainly used by the "Store" behavior to reset the accumulated list. |

### Outputs

| Name | Type | Description |
|------|------|-------------|
| Output Count | Jolt Output | Number of blocks currently in the Output list. Re-fired every time the result changes, so it can also be used as a "watcher" on the A/B inputs. |
| Output | Tag Output | Resulting list of blocks produced by the selected Behavior. Connect to a [block_foreach](/blocks/system/block_foreach), to another Tag input, or to a [get_name](/blocks/system/get_name) for debugging. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Behavior | Selector | How to combine A and B into the Output. See the long description for the full list of behaviors. |

## Related Blocks

- [block_foreach](/blocks/system/block_foreach)
- [block_spawn](/blocks/system/block_spawn)
- [block_remove](/blocks/system/block_remove)
- [all_with_variable](/blocks/system/all_with_variable)
- [get_variable](/blocks/system/get_variable)
- [get_name](/blocks/system/get_name)
- [raycast](/blocks/controllers/raycast)
- [trigger_box](/blocks/players/trigger_box)

---