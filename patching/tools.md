---
title: Patchworld MCP Tools Reference
description: Auto-generated list of available Patchworld MCP tools.
published: true
date: 2026-05-27T23:51:20.699Z
tags: patching, mcp, patchworld, tools
editor: markdown
dateCreated: 2026-05-27T23:51:20.699Z
---

# Patchworld MCP Tools Reference

This document lists all the MCP tools exposed by the Patchworld app. These tools are dynamically synchronized from the C# source code inside the `NewPatch` repository.

## Tools Index

| Tool Name | Description Summary |
| --- | --- |
| [`list_objects`](#list_objects) | Get minimal scene overview: object IDs, names, types, positions, and connection counts. |
| [`spawn_object`](#spawn_object) | Create a new object in the world. |
| [`set_input_value`](#set_input_value) | Set a value on a stream input. |
| [`disconnect_objects`](#disconnect_objects) | Disconnect/remove connections between objects (stream, jolt, or selector connections). |
| [`connect_objects`](#connect_objects) | Connect two objects. |
| [`inspect_runtime_value`](#inspect_runtime_value) | Read the current live engine value at one or more stream ports. |
| [`delete_objects`](#delete_objects) | Delete one or more objects from the world. |
| [`select_objects`](#select_objects) | Select objects for further operations. |
| [`get_object_info`](#get_object_info) | Get detailed information about a specific object including its inputs, outputs, documentation, and properties. |
| [`create_text`](#create_text) | Create a text display object (txt block) in the 3D world that shows text visually. |
| [`set_property`](#set_property) | Set an inspector property on an object. |
| [`transform_object`](#transform_object) | Move and/or rotate an object. |
| [`get_patch_serialization`](#get_patch_serialization) | Return the full current scene as PatchWorld's canonical . |
| [`apply_patch_serialization`](#apply_patch_serialization) | Replace the current scene by loading a full . |
| [`edit_patch_serialization`](#edit_patch_serialization) | Surgical text edit on the current scene serialization. |
| [`restore_snapshot`](#restore_snapshot) | Restore the most recent auto-snapshot taken by apply_patch_serialization or edit_patch_serialization. |
| [`clear_ai_labels`](#clear_ai_labels) | Clear every AI label the current session has assigned (the friendly names set via spawn_object name: or surfaced as label:\"…\" in list_objects). |
| [`set_typedial`](#set_typedial) | Set a TypeDial (dropdown) on a block. |
| [`list_block_types`](#list_block_types) | Discover spawnable block types — same catalog and same categories used by PatchWorld's in-app block library. |
| [`get_block_doc`](#get_block_doc) | Get the full documentation for one block type — description, longDescription, and the parts list (stream/jolt I/O, selectors, type dials). |
| [`take_photo`](#take_photo) | Capture a photograph of the current scene and return it as image content. |
| [`apply_commands`](#apply_commands) | PREFERRED for any operation that requires more than ONE tool call. |
| [`enter_subpatch`](#enter_subpatch) | Step INTO a subpatch (device, instrument, group) so subsequent tools operate on its inner blocks. |
| [`exit_subpatch`](#exit_subpatch) | Step OUT of the current subpatch back to its parent scope (one level). |
| [`get_scope`](#get_scope) | Return the current scope path as a list from root to leaf. |
| [`group_objects`](#group_objects) | Wrap the listed blocks into a new subpatch (group) in the current scope. |
| [`ungroup_subpatch`](#ungroup_subpatch) | Dissolve a subpatch: its children move up into the parent scope, the wrapper is removed. |

---

## Tools Directory

### list_objects

Get minimal scene overview: object IDs, names, types, positions, and connection counts. Use get_object_info for detailed information about specific objects. Pass verbose:true for the full .patch serialization (or call get_patch_serialization directly).

*No parameters required.*

---

### spawn_object

Create a new object in the world

*No parameters required.*

---

### set_input_value

Set a value on a stream input. Returns the updated object state after modification. input_index accepts either a numeric index or the stream input's doc name (e.g. 'Frequency (Hz)', 'Phase offset').

*No parameters required.*

---

### disconnect_objects

Disconnect/remove connections between objects (stream, jolt, or selector connections). IMPORTANT CONNECTION RULES: Jolts CAN connect to stream inputs (jolt outputs → stream inputs), but streams CANNOT directly connect to jolt inputs (use 'stoe' block to convert stream to jolt). For streams, this handles both direct connections and connections that go through internal fork systems.\n\nPORT ADDRESSING: output_index and input_index accept either a numeric index OR the port's doc name (e.g. 'Signal output', 'Frequency (Hz)'). Names are matched case-insensitive against the labels get_object_info prints; substring matches are accepted. Name resolution applies to stream / jolt / jolt_to_stream only — selector/tag/stick still require numeric indices.

*No parameters required.*

---

### connect_objects

Connect two objects.

CONNECTION TYPES (connection_type is OPTIONAL — inferred from port kinds when omitted):
- 'stream': stream output -> stream input. output_index/input_index reference the indexed Stream Outputs/Inputs from get_object_info.
- 'jolt': jolt output -> jolt input. Indices reference Jolt Outputs/Inputs from get_object_info.
- 'jolt_to_stream': jolt output -> stream input. The platform supports this natively (drag a jolt cable onto a stream knob). output_index = jolt-output index on source; input_index = stream-input index on target.
- 'selector' / 'tag' / 'stick': pass-through reference. Source is the object being referenced (e.g., shape) and target is the manipulation block (e.g., block_set_color). Selector connections go FROM any object TO blocks with selector inputs. THESE REQUIRE EXPLICIT connection_type — they aren't tied to numeric stream/jolt ports and can't be inferred.

CONNECTION TYPE INFERENCE (when connection_type is omitted):
- Stream Output -> Stream Input -> 'stream'
- Jolt Output   -> Jolt Input   -> 'jolt'
- Jolt Output   -> Stream Input -> 'jolt_to_stream'
- Stream Output -> Jolt Input   -> ERROR (returns UNSUPPORTED_PAIR with stoe-bridge suggestion)
When connection_type is provided explicitly, it is validated against the inferred type; a mismatch returns PORT_KIND_MISMATCH.

PORT ADDRESSING: output_index and input_index accept either a numeric index OR the port's doc name (e.g. 'Signal output', 'Emitter', 'Frequency (Hz)'). Names are matched case-insensitive against the labels get_object_info prints; substring matches are accepted ('freq' resolves to 'Frequency (Hz)'). Name resolution applies to stream / jolt / jolt_to_stream only — selector/tag/stick still require numeric indices.

ERROR FORMAT: failures return 'ERROR: <line>\n<JSON block>' with error_code in {PORT_NOT_FOUND, PORT_KIND_MISMATCH, UNSUPPORTED_PAIR, OBJECT_NOT_FOUND} and a suggested_fix payload. Parse the JSON with JObject.Parse(text.Substring(text.IndexOf('{'))).

Stream output -> jolt input is NOT supported directly; the structured error includes the 'stoe' bridge steps to take.

*No parameters required.*

---

### inspect_runtime_value

Read the current live engine value at one or more stream ports. Use this to diagnose what a block is actually outputting or receiving right now — e.g. oscillator frequency, counter current count, envelope output level.

Accepts a list of (object, port) targets, or the shortcut form (object, port) for a single read. Port can be a name from get_object_info (e.g. 'Frequency (Hz)', 'Signal output') or a numeric index into the stream-input or stream-output array. Pass port:'*' to read all stream inputs on a block at once.

Returns numeric snapshots, not audio buffers. Audio-rate outputs (e.g. 'Signal output' on an oscillator) return whatever sample the engine last computed — bouncing between -1 and +1 thousands of times a second — so the snapshot is meaningless on its own; read the driving stream input instead to diagnose state. Jolt ports are NOT supported (they are events, not values); read the upstream stream instead.

Read-only, side-effect-free, synchronous. Cheap; use freely during debugging.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `targets` | `array` |  |

---

### delete_objects

Delete one or more objects from the world

*No parameters required.*

---

### select_objects

Select objects for further operations

*No parameters required.*

---

### get_object_info

Get detailed information about a specific object including its inputs, outputs, documentation, and properties. Returns a human-readable prose response. Pass include_schema:true to append a machine-readable JSON schema block fenced by '=== Schema ===' (useful for tool-chaining; off by default to save tokens). For subpatches/devices, only user-facing controls (children not marked 'Hide from Play') and externally-wired boundary ports are listed by default; pass show_all:true for the full unfiltered dump.

*No parameters required.*

---

### create_text

Create a text display object (txt block) in the 3D world that shows text visually. Use this to add labels, titles, or any visible text in the scene.

*No parameters required.*

---

### set_property

Set an inspector property on an object. Use get_object_info first to see available properties. Can set TypeDial options (waveform, filter type), input values, colors, visibility, scale, etc.

*No parameters required.*

---

### transform_object

Move and/or rotate an object. At least one of 'position' or 'rotation' must be provided. Both are optional so this can be used for pure translation, pure rotation, or both at once.

*No parameters required.*

---

### get_patch_serialization

Return the full current scene as PatchWorld's canonical .patch text — the same format used to save/load patches. Use this for bulk context (whole-scene overview) instead of repeatedly calling list_objects + get_object_info. Read-only.

*No parameters required.*

---

### apply_patch_serialization

Replace the current scene by loading a full .patch text. Use this for FULL-SCENE rewrites or composing whole new patches from scratch.

DO NOT USE THIS FOR SINGLE-FIELD CHANGES. To tweak one value:
  - stream input value -> set_input_value
  - position / rotation -> transform_object
  - block property -> set_property
  - a few targeted edits inside the serialization -> edit_patch_serialization (find/replace, way cheaper than emitting the whole text)

The pre-load scene is auto-snapshotted via BackupPatch.CurrentStateToTemp; if the load wedges the scene, call restore_snapshot to roll back.

The load runs as a Unity coroutine that completes across several frames. This tool returns 'Load started' immediately; verify with list_objects or get_patch_serialization a moment later.

The 'text' must be the FULL .patch document (header + scene_settings + spawn + connections), not a fragment.

*No parameters required.*

---

### edit_patch_serialization

Surgical text edit on the current scene serialization. Reads the current .patch text, replaces 'find' with 'replace' exactly once, then applies the result. Far cheaper than apply_patch_serialization when only a few characters change.

STRICT MATCH: 'find' must appear EXACTLY ONCE in the current serialization. If it appears zero times the edit is wrong; if it appears more than once the edit is ambiguous — in both cases this tool errors without touching the scene. To disambiguate, include enough surrounding context in 'find' to make it unique.

Pre-edit state is auto-snapshotted (use restore_snapshot to roll back).

EXAMPLE: change an oscillator's frequency from 220 to 80 (assuming '~:[220|0|s 0|0|s]' appears only once in the scene):
  { find: '~:[220|0|s 0|0|s]', replace: '~:[80|0|s 0|0|s]' }

*No parameters required.*

---

### restore_snapshot

Restore the most recent auto-snapshot taken by apply_patch_serialization or edit_patch_serialization. Use this if a load wedges the scene or produces unexpected state. The snapshot is overwritten on the next apply/edit, so only the last operation can be undone. NOTE: restoring is a full reload — every object gets a fresh numeric ID. AI labels are re-mapped to the new IDs by type+position. Any raw numeric IDs you captured before the snapshot will be stale; re-read with list_objects to get current IDs.

*No parameters required.*

---

### clear_ai_labels

Clear every AI label the current session has assigned (the friendly names set via spawn_object name: or surfaced as label:\"…\" in list_objects). Call this BEFORE apply_patch_serialization when you intend to load a completely unrelated patch — otherwise the label remap may carry old names onto new blocks at matching type+position. Also useful when starting fresh on the same scene. After clearing, list_objects shows blocks without labels; you can re-label by spawning or via future label_object verbs. Returns the number of labels cleared.

*No parameters required.*

---

### set_typedial

Set a TypeDial (dropdown) on a block. Use this when set_property fails on a property listed as '[Dial] X (dropdown)' in get_object_info — the inspector path can null-ref on TypeDial-backed controls; this tool calls the underlying InteractiveTypeDial directly.

The 'value' can be either the integer index or the option label (case-insensitive). The 'dial_name' may be omitted if the target has exactly one TypeDial.

*No parameters required.*

---

### list_block_types

Discover spawnable block types — same catalog and same categories used by PatchWorld's in-app block library. With no args, returns the full catalog grouped by category and lists every valid category in a 'Categories: …' header you can pivot off. Use 'category' to browse one category (Audio, Visual, Controllers, Motion, Interfaces, …), 'search' for substring match against name + display name + description (same semantics as the library's search box), or both. Each row reports: name | displayName | port counts | one-line description. Names returned here are valid as the 'type' arg of spawn_object — pair with get_block_doc(name) for full per-block detail before spawning.

*No parameters required.*

---

### get_block_doc

Get the full documentation for one block type — description, longDescription, and the parts list (stream/jolt I/O, selectors, type dials). Same content surfaced in get_object_info's 'Block Documentation' section, but addressable by block name without needing an existing instance. Use after list_block_types to inspect a candidate before spawning.

*No parameters required.*

---

### take_photo

Capture a photograph of the current scene and return it as image content. Use this to orient yourself spatially when text scene info (list_objects, get_object_info) isn't enough — e.g. "is this cluttered," "what's behind the speaker," "does the visualizer overlap the shape," "where's the gap for a new block."

MODES:
- No args: cold-start auto-frame. A temporary internal camera bounding-boxes the current scope and renders one isometric shot. Use this for first-look orientation when you don't know what's in the scene.
- cameras: [<name_or_id>, ...]: renders through one or more existing MuXCam blocks in the scene. One image per camera, in order. Users can pre-place named cameras (overview_cam, front_cam, ...) and you can ask for them by name.

RESPONSE: an MCP content array containing a text block (camera identity + a JSON sidecar mapping object IDs to screen-space coords) and one image per rendered camera. The sidecar lets you correlate "thing at (320, 240)" → "id:1611030452" without overlay text on the image.

COST AWARENESS: each camera produces an independent image; vision tokens scale with image count × resolution. Prefer one well-chosen camera; only request multi-angle when you genuinely need to compare views.

LIMITATIONS:
- MuXCam has no "look at scene object" property. To aim a camera at a block, use transform_object with a manually-computed rotation. There is no set_property("look_at"

*No parameters required.*

---

### apply_commands

PREFERRED for any operation that requires more than ONE tool call. Bundle multiple tool calls into a single round-trip — much faster and cheaper than calling tools one at a time. The other tools in this catalog (spawn_object, transform_object, connect_objects, set_input_value, etc.) should be wrapped in apply_commands whenever you plan to call any of them in sequence.

WHEN TO USE: spawning a patch (multiple spawn_objects + connects), reconfiguring several blocks, deleting many things at once, or any plan with 2+ tool calls.

SHAPE: { commands: [{ tool: <tool_name>, args: <args object> }, ...] }. Each entry uses the same tool name and args as if calling that tool directly. Steps run sequentially; later steps see earlier effects, so step 2 can reference an object named in step 1 (use spawn_object's optional 'name' arg to make this work).

EXAMPLE: spawn an osc and a speaker, then connect them:
{
  "commands": [
    {"tool": "spawn_object"

*No parameters required.*

---

### enter_subpatch

Step INTO a subpatch (device, instrument, group) so subsequent tools operate on its inner blocks. After this call, list_objects / spawn_object / connect_objects / get_object_info all see the subpatch's contents instead of the scene root. Use exit_subpatch to leave. Nested enter is allowed.

Side effects: the local user's view enters the subpatch (Edit mode forced). MP peers receive the scope change so collaborative view stays consistent.

*No parameters required.*

---

### exit_subpatch

Step OUT of the current subpatch back to its parent scope (one level). At root, returns an informational no-op (not an error). Inverse of enter_subpatch.

*No parameters required.*

---

### get_scope

Return the current scope path as a list from root to leaf. Each entry is {id, name}; root is reported as {id:0, name:'scene'}. Use to confirm where subsequent tool calls will operate before mutating.

*No parameters required.*

---

### group_objects

Wrap the listed blocks into a new subpatch (group) in the current scope. All targets must already be in the current scope; cross-scope grouping is rejected.

IMPORTANT: any wire that crossed the new group boundary is SEVERED (not auto-promoted to a boundary port). To preserve a wire that connected a grouped block to an outside block, re-issue connect_objects via the subpatch's boundary after grouping.

*No parameters required.*

---

### ungroup_subpatch

Dissolve a subpatch: its children move up into the parent scope, the wrapper is removed. The subpatch must be a direct child of the current scope.

IMPORTANT: wires crossing the (former) subpatch boundary are SEVERED on ungroup, matching the human VR flow. Use disconnect_objects + connect_objects manually if you need wires to survive a round-trip.

*No parameters required.*

---
