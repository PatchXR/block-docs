---
title: Patchworld MCP Tools Reference
description: Auto-updated Patchworld MCP Tools Reference
published: true
date: 2026-06-07T12:41:06.095Z
tags: patching, mcp, patchworld, tools
editor: markdown
dateCreated: 2026-05-27T23:51:20.699Z
---

# Patchworld MCP Tools Reference

This document lists all the MCP tools exposed by the Patchworld app. These tools are dynamically synchronized from the C# source code inside the `NewPatch` repository.

## Tools Index

| Tool Name | Description Summary |
| --- | --- |
| [`list_objects`](#list_objects) | Get a scene overview as JSON: {scope, total, offset, count, objects:[{id,name,type,position,visible,ports?{stream_in,stream_out,jolt_in,jolt_out,selector_in},src?,attach?,label?}], connection_count, connections:[{kind:'stream'|'jolt'|'stick', from:{id,port?}, to:[{id,port?},…]}]}. |
| [`spawn_object`](#spawn_object) | Create a new object in the world. |
| [`set_input_value`](#set_input_value) | Set a value on a stream input. |
| [`disconnect_objects`](#disconnect_objects) | Disconnect/remove connections between objects (stream, jolt, or selector connections). |
| [`connect_objects`](#connect_objects) | Connect two objects. |
| [`inspect_runtime_value`](#inspect_runtime_value) | Read the current live engine value at one or more stream ports. |
| [`delete_objects`](#delete_objects) | Delete one or more objects from the world. |
| [`select_objects`](#select_objects) | Select objects for further operations. |
| [`get_selection`](#get_selection) | Read the objects the USER has currently selected in VR (via the controller grip / sphere-select tool). |
| [`get_object_info`](#get_object_info) | Get detailed information about a specific object — inputs, outputs, dials, (optionally) documentation and properties. |
| [`create_text`](#create_text) | Create a text display object (txt block) in the 3D world that shows text visually. |
| [`set_text`](#set_text) | Set the text content of a block that has an editable text field — e. |
| [`set_property`](#set_property) | Set an inspector property on an object. |
| [`transform_object`](#transform_object) | Move and/or rotate an object. |
| [`get_patch_serialization`](#get_patch_serialization) | Return the full current scene as PatchWorld's canonical. |
| [`edit_patch_serialization`](#edit_patch_serialization) | Surgical text edit on the current scene serialization. |
| [`restore_snapshot`](#restore_snapshot) | Restore the most recent auto-snapshot taken before an edit_patch_serialization. |
| [`set_typedial`](#set_typedial) | Set a TypeDial (dropdown) on a block. |
| [`list_block_types`](#list_block_types) | Discover spawnable block types — same catalog and categories used by PatchWorld's in-app block library. |
| [`get_block_doc`](#get_block_doc) | Get the full documentation for one block type as JSON — {name, displayName, description, longDescription, parts:[…], categories, tags}. |
| [`take_photo`](#take_photo) | Capture a photograph of the current scene and return it as image content. |
| [`apply_commands`](#apply_commands) | PREFERRED for any operation that requires more than ONE tool call. |
| [`enter_subpatch`](#enter_subpatch) | Step INTO a subpatch (device, instrument, group) so subsequent tools operate on its inner blocks. |
| [`exit_subpatch`](#exit_subpatch) | Step OUT of the current subpatch back to its parent scope (one level). |
| [`get_scope`](#get_scope) | Return the current scope path as a list from root to leaf. |
| [`diagnose_streams`](#diagnose_streams) | h21 P0 (read-only): derive the logical stream-edge view from the current fork plumbing and report structural inconsistencies. |
| [`group_objects`](#group_objects) | Wrap the listed blocks into a new subpatch (group) in the current scope. |
| [`ungroup_subpatch`](#ungroup_subpatch) | Dissolve a subpatch: its children move up into the parent scope, the wrapper is removed. |

---

## Tools Directory

### list_objects

Get a scene overview as JSON: {scope, total, offset, count, objects:[{id,name,type,position,visible,ports?{stream_in,stream_out,jolt_in,jolt_out,selector_in},src?,attach?,label?}], connection_count, connections:[{kind:'stream'|'jolt'|'stick', from:{id,port?}, to:[{id,port?},…]}]}. Connections are fan-out-grouped: each entry is one source feeding a 'to' array of targets (connection_count is the total wire count). Ports/connections resolve to the current scope (a subpatch's internal wiring collapses unless you enter it). Use get_object_info for per-object detail, get_patch_serialization for canonical .patch text. On large scenes use filter, limit/offset to page the object roster, and include_connections:false to drop the connection array.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `filter` | `string` | Optional case-insensitive substring filter on object name. |
| `offset` | `integer` | Roster pagination: skip the first N objects (default 0). Connections are unaffected (always full scope). |
| `limit` | `integer` | Roster pagination: return at most N objects (default: all). Use with offset to page. 'total' in the response is the full unpaginated count. |
| `include_connections` | `boolean` | Include the connections array (default true). Set false to omit it entirely on large scenes where you only need the object roster. |

---

### spawn_object

Create a new object in the world

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `type` | `string` | Block name to spawn. Use list_block_types for the full catalog of spawnable types (categories match the in-app library). Some short aliases also work (e.g. 'osc' → oscillator), but the canonical name from list_block_types is always safe. |
| `parameters` | `string` | Optional parameters for the object (e.g., 'freq:440' for oscillator) |
| `position` | `array` | Optional 3D position [x, y, z] |
| `name` | `string` | Optional label that replaces the default block name (e.g., 'kick_drum', 'M1'). Surfaces in list_objects so you can refer to the object later without juggling 10-digit IDs. |

---

### set_input_value

Set a value on a stream input. Returns the updated object state after modification. input_index accepts either a numeric index or the stream input's doc name (e.g. 'Frequency (Hz)', 'Phase offset').

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `object_name` | `string` | Name or ID of the target object |
| `input_index` | `string` | Stream input to set — either a 0-based numeric index or the port's doc name (e.g. 'Frequency (Hz)'). Names are matched case-insensitive; substring matches are accepted. |
| `value` | `number` | The value to set |
| `exp` | `integer` | Exponent for precision (default -2 for fine control) |
| `is_float` | `boolean` | Whether value should be treated as continuous float (default false for stepped) |

---

### disconnect_objects

Disconnect/remove connections between objects (stream, jolt, or selector connections). IMPORTANT CONNECTION RULES: Jolts CAN connect to stream inputs (jolt outputs → stream inputs), but streams CANNOT directly connect to jolt inputs (use 'stoe' block to convert stream to jolt). For streams, this handles both direct connections and connections that go through internal fork systems.\n\nPORT ADDRESSING: output_index and input_index accept either a numeric index OR the port's doc name (e.g. 'Signal output', 'Frequency (Hz)'). Names are matched case-insensitive against the labels get_object_info prints; substring matches are accepted. Name resolution applies to stream / jolt / jolt_to_stream only — selector/tag/stick still require numeric indices.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `source` | `string` | Source object name or ID |
| `target` | `string` | Target object name or ID |
| `output_index` | `string` | Output port on source (default 0). Numeric index or port name from the block doc (e.g. 'Signal output'). |
| `input_index` | `string` | Input port on target (default 0). Numeric index or port name from the block doc (e.g. 'Frequency (Hz)'). |
| `connection_type` | `string` | Connection type: 'stream' (default), 'jolt', 'jolt_to_stream', or 'selector' |

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

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `source` | `string` | Source object name or ID |
| `target` | `string` | Target object name or ID |
| `output_index` | `string` | Output port on source (default 0). Numeric index (e.g. 0, 1) or port name from the block doc (e.g. 'Signal output', 'Emitter'). See get_object_info or get_block_doc for available names. |
| `input_index` | `string` | Input port on target (default 0). Numeric index (e.g. 0, 1) or port name from the block doc (e.g. 'Frequency (Hz)', 'Increment'). See get_object_info or get_block_doc for available names. |
| `connection_type` | `string` | Optional. When omitted, inferred from the source/target port types (Stream Output -> Stream Input = stream; Jolt Output -> Jolt Input = jolt; Jolt Output -> Stream Input = jolt_to_stream). Specify explicitly only when overriding the inferred type or when using selector/tag/stick (those can't be inferred from ports). When provided, it is validated against the inferred type and mismatches return PORT_KIND_MISMATCH. |

---

### inspect_runtime_value

Read the current live engine value at one or more stream ports. Use this to diagnose what a block is actually outputting or receiving right now — e.g. oscillator frequency, counter current count, envelope output level.

Accepts a list of (object, port) targets, or the shortcut form (object, port) for a single read. Port can be a name from get_object_info (e.g. 'Frequency (Hz)', 'Signal output') or a numeric index into the stream-input or stream-output array. Pass port:'*' to read all stream inputs on a block at once.

Returns numeric snapshots, not audio buffers. Audio-rate outputs (e.g. 'Signal output' on an oscillator) return whatever sample the engine last computed — bouncing between -1 and +1 thousands of times a second — so the snapshot is meaningless on its own; read the driving stream input instead to diagnose state. Jolt ports are NOT supported (they are events, not values); read the upstream stream instead.

Read-only, side-effect-free, synchronous. Cheap; use freely during debugging.

Always returns a compact JSON object ({"values":[...]}) — agent-facing, no prose.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `targets` | `array` | List of { object, port } pairs to read. Each item: { object: name-or-id, port: name-or-index-or-'*' }. Omit when using the shortcut form (object + port). |
| `object` | `string` | Object name or ID |
| `port` | `string` | Port name, numeric index, or '*' for all stream inputs |
| `object` | `string` | Shortcut: single target object name or ID (used when 'targets' is omitted) |
| `port` | `string` | Shortcut: single target port name, numeric index, or '*' for all stream inputs |
| `max` | `integer` | Optional cap on number of targets read (default 16). Pass 0 for unbounded; >64 logs a fan-out warning. |

---

### delete_objects

Delete one or more objects from the world

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `targets` | `array` | List of object names or IDs to delete |

---

### select_objects

Select objects for further operations

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `targets` | `array` | List of object names or IDs to select |

---

### get_selection

Read the objects the USER has currently selected in VR (via the controller grip / sphere-select tool). Read-only; returns JSON {count, objects:[{id,type,name,position,label?,parts?}]} (count:0 when nothing is selected). Use this when the user refers to 'this', 'these', 'the selected ones', or 'what I picked' so you know which objects to operate on without asking them to name IDs. Note: this is the live user selection and is independent of select_objects (which sets the AI's own selection).

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `include_parts` | `boolean` | If true, also list the individual sub-parts of each selected object. Default false (objects only). |

---

### get_object_info

Get detailed information about a specific object — inputs, outputs, dials, (optionally) documentation and properties. ALWAYS returns a compact JSON object (agent-facing; no prose). Default sections: base (transform/label), ports, dials. Use include_doc/include_properties to add those sections, or fields to restrict to specific sections. For subpatches/devices, only user-facing controls (children not marked 'Hide from Play') and externally-wired boundary ports are listed by default; pass show_all:true for the full unfiltered dump.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `identifier` | `string` | Object name or ID to get info about |
| `show_all` | `boolean` | Subpatches only: include hidden inner blocks and unwired boundary ports (default false). When false, only children with 'Hide from Play' unchecked and externally-wired boundary ports are listed. Ignored for non-subpatch blocks. |
| `include_doc` | `boolean` | If true, adds a 'doc' section (the static Block Documentation) to the JSON. Default false (use get_block_doc instead) to save context window tokens. |
| `include_properties` | `boolean` | If true, adds a 'properties' array (inspector properties) to the JSON. Default false to save context window tokens. |
| `fields` | `array` | Optional section filter. E.g. [\ |

---

### create_text

Create a text display object (txt block) in the 3D world that shows text visually. Use this to add labels, titles, or any visible text in the scene.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `text` | `string` | The text content to display in the scene |
| `position` | `array` | Optional 3D position [x, y, z] for the text object |

---

### set_text

Set the text content of a block that has an editable text field — e.g. a txt label block, a wireless stream/jolt send or receive block (its channel name), or an execute block (its command string). Call get_object_info first and read the 'text_inputs' array ({index, value}) to see which fields a block exposes; a block with no text_inputs has no text to set. This fires the block's commit logic so the change actually takes effect: renaming a wireless block re-routes it to the new channel, and an execute block re-parses its command. For wireless blocks the result reports how many senders/receivers now share the channel. Multi-line text is supported — embed newlines (\n) directly in 'text' (e.g. multi-statement execute commands).

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `object_name` | `string` | Name or ID of the block whose text field to set |
| `text` | `string` | New text content. May contain newlines (\\n) for multi-line fields like execute commands. Pass an empty string to clear the field. |
| `input_index` | `integer` | Which text field to set when a block exposes more than one (default 0). See get_object_info -> text_inputs for the indices. |

---

### set_property

Set an inspector property on an object. Use get_object_info first to see available properties. Can set TypeDial options (waveform, filter type), input values, colors, visibility, scale, etc.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `object_name` | `string` | Object name or ID to modify |
| `property_name` | `string` | Property name (e.g., 'Generators', 'Scale', 'Color', 'Hidden'). Use index like 'Input[0]' for stream inputs. |
| `value` | `string` | Value to set. For dropdowns: option name (e.g., 'sin', 'sqr') or index. For bool: 'true'/'false'. For color: 'R,G,B' or 'R,G,B,A'. For vector3: 'X,Y,Z'. For numbers: numeric value. |

---

### transform_object

Move and/or rotate an object. At least one of 'position' or 'rotation' must be provided. Both are optional so this can be used for pure translation, pure rotation, or both at once.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `object_name` | `string` | Object name or ID to transform |
| `position` | `array` | Optional target position as [x, y, z] in meters |
| `rotation` | `array` | Optional rotation as Euler angles [x, y, z] in degrees |
| `relative` | `boolean` | If true, position/rotation are offsets from current values. Default: false (absolute) |

---

### get_patch_serialization

Return the full current scene as PatchWorld's canonical .patch text — the same format used to save/load patches. Use this for bulk context (whole-scene overview) instead of repeatedly calling list_objects + get_object_info. Read-only.

BLOB HANDLES: opaque engine data (the data:/hash:/version: fields — compressed subpatch internals and identity bytes) is shown as a short handle like 'data:<<BLOB|data|1105327234|4486|3f9ac1d2e0b47a55>>' instead of raw base64. These are NOT editable text — they round-trip automatically: copy a handle verbatim into edit_patch_serialization and the real bytes are restored server-side. Never split, alter, or invent one. To read or change a subpatch's INTERNAL contents, enter_subpatch into it and call get_patch_serialization there.

STREAM FORK PLUMBING: grey-painted blocks literally named 'fork'/'fork_output', and the signature triple 'src <:[[fork 0]]' then 'fork SEL:[0 [visibles:[1] parts:[[fork_output 0]]]]' then 'fork_output <:[[dst 0]]', are the engine's internal routing for ONE logical stream wire (src -> dst). They are plumbing, not user blocks — do NOT hand-edit or hand-author them; create and destroy stream wires via connect_objects / disconnect_objects, which manage the fork chain for you. A cross-scope wire references the inner endpoint as 'subpatchId/innerId'.

*No parameters required.*

---

### edit_patch_serialization

Surgical text edit on the current scene serialization. Reads the current .patch text, replaces 'find' with 'replace' exactly once, then applies the result. The right tool for small, targeted changes — far cheaper and safer than re-emitting the whole scene.

STRICT MATCH: 'find' must appear EXACTLY ONCE in the current serialization. If it appears zero times the edit is wrong; if it appears more than once the edit is ambiguous — in both cases this tool errors without touching the scene. To disambiguate, include enough surrounding context in 'find' to make it unique.

Pre-edit state is auto-snapshotted (use restore_snapshot to roll back).

EXAMPLE: change an oscillator's frequency from 220 to 80 (assuming '~:[220|0|s 0|0|s]' appears only once in the scene):
  { find: '~:[220|0|s 0|0|s]', replace: '~:[80|0|s 0|0|s]' }

BLOB HANDLES: opaque fields appear as 'data:<<BLOB|...>>' etc. Edit the readable text around them; never put a handle inside 'find' partially or alter one in 'replace'. Handles left intact are restored to real bytes automatically; a broken handle is rejected without touching the scene. To edit a subpatch's internals, enter_subpatch first.

DON'T hand-edit stream fork plumbing: the 'fork'/'fork_output' blocks and their 'src <:[[fork]]' / 'fork SEL:[...parts:[[fork_output]]]' / 'fork_output <:[[dst]]' triple are engine-managed routing for one logical stream wire. Re-route streams with connect_objects / disconnect_objects, not by editing these tokens — a half-edited fork chain produces orphan plumbing or silent unfed targets.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `find` | `string` | Exact substring to find in the current serialization. Must match exactly once. |
| `replace` | `string` | Substring to put in its place. |

---

### restore_snapshot

Restore the most recent auto-snapshot taken before an edit_patch_serialization. Use this if an edit wedges the scene or produces unexpected state. The snapshot is overwritten on the next edit, so only the last operation can be undone. NOTE: restoring is a full reload — every object gets a fresh numeric ID. AI labels are preserved (they ride the snapshot's ai_meta and re-map to the new IDs automatically). Any raw numeric IDs you captured before the snapshot will be stale; re-read with list_objects to get current IDs.

*No parameters required.*

---

### set_typedial

Set a TypeDial (dropdown) on a block. Use this when set_property fails on a property listed as '[Dial] X (dropdown)' in get_object_info — the inspector path can null-ref on TypeDial-backed controls; this tool calls the underlying InteractiveTypeDial directly.

The 'value' can be either the integer index or the option label (case-insensitive). The 'dial_name' may be omitted if the target has exactly one TypeDial.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `object_name` | `string` | Object name or numeric ID. |
| `dial_name` | `string` | TypeDial identifier — accepts the block doc's parts[].name (the same label get_block_doc / get_object_info print, e.g. 'Operation', 'Wave Type'), or the DialType enum name (e.g. 'Generators', 'StreamOperation'). Matched case-insensitive, exact first then substring. Omit if the block has only one dial. |
| `value` | `string` | Integer index (e.g. '2') or option label (e.g. 'tri'). |

---

### list_block_types

Discover spawnable block types — same catalog and categories used by PatchWorld's in-app block library. Returns JSON {categories:[…], count, blocks:[{name, display_name, categories, ports, description}]}; the top-level 'categories' lists every valid category to pivot off. Use 'category' to browse one category (Audio, Visual, Controllers, Motion, Interfaces, …), 'search' for substring match against name + display name + description, or both. 'name' is valid as the 'type' arg of spawn_object — pair with get_block_doc(name) for full per-block detail before spawning.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `category` | `string` | Optional category filter (case-insensitive). Use the same names shown in the in-app library. Call with no args first if you don't know the valid set — the response always lists them in a 'Categories: …' header. |
| `search` | `string` | Optional substring match against name + displayName + description. Same semantics as the library's search box. |

---

### get_block_doc

Get the full documentation for one block type as JSON — {name, displayName, description, longDescription, parts:[…], categories, tags}. parts covers stream/jolt I/O, selectors, type dials. Same data as get_object_info's include_doc 'doc' section, but addressable by block name without needing an existing instance. Use after list_block_types to inspect a candidate before spawning.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `name` | `string` | Block name as returned by list_block_types (e.g. 'oscillator', 'noise', 'filter'). |

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

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `cameras` | `array` | Optional list of camera names or IDs. Omit (or empty) for cold-start auto-frame using a temporary internal camera. |
| `annotate` | `boolean` | If true (default), include a JSON sidecar mapping visible object IDs to screen coords. Set false to skip the sidecar for a cheaper response. |
| `width` | `integer` | Image width in pixels. Default 768. Vision tokens scale with area — 512 is enough for spatial reasoning. |
| `height` | `integer` | Image height in pixels. Default 768. |
| `format` | `string` | Image format: 'jpeg' (default, ~5-10× smaller payload) or 'png' (pixel-perfect, use only when fine detail matters). |
| `max_objects` | `integer` | Cap on sidecar entries per camera (default 30, ordered by screen-bbox area descending). Pass 0 for everything; use sparingly on dense scenes. |

---

### apply_commands

PREFERRED for any operation that requires more than ONE tool call. Bundle multiple tool calls into a single round-trip — much faster and cheaper than calling tools one at a time. The other tools in this catalog (spawn_object, transform_object, connect_objects, set_input_value, etc.) should be wrapped in apply_commands whenever you plan to call any of them in sequence.

WHEN TO USE: spawning a patch (multiple spawn_objects + connects), reconfiguring several blocks, deleting many things at once, or any plan with 2+ tool calls.

SHAPE: { commands: [{ tool: <tool_name>, args: <args object> }, ...] }. Each entry uses the same tool name and args as if calling that tool directly. Steps run sequentially; later steps see earlier effects, so step 2 can reference an object named in step 1 (use spawn_object's optional 'name' arg to make this work).

EXAMPLE: spawn an osc and a speaker, then connect them:
{
  "commands": [
    {"tool": "spawn_object"

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `commands` | `array` | Ordered list of tool calls to execute. |
| `tool` | `string` | Tool name (e.g. 'spawn_object', 'transform_object', 'connect_objects') |
| `args` | `object` | Arguments object for that tool, same shape as if calling it directly. |

---

### enter_subpatch

Step INTO a subpatch (device, instrument, group) so subsequent tools operate on its inner blocks. After this call, list_objects / spawn_object / connect_objects / get_object_info all see the subpatch's contents instead of the scene root. Use exit_subpatch to leave. Nested enter is allowed.

Side effects: the local user's view enters the subpatch (Edit mode forced). MP peers receive the scope change so collaborative view stays consistent.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `identifier` | `string` | Subpatch object id, AI label, or name (anything FindObject resolves). Must be a subpatch. |

---

### exit_subpatch

Step OUT of the current subpatch back to its parent scope (one level). At root, returns an informational no-op (not an error). Inverse of enter_subpatch.

*No parameters required.*

---

### get_scope

Return the current scope path as a list from root to leaf. Each entry is {id, name}; root is reported as {id:0, name:'scene'}. Use to confirm where subsequent tool calls will operate before mutating.

*No parameters required.*

---

### diagnose_streams

h21 P0 (read-only): derive the logical stream-edge view from the current fork plumbing and report structural inconsistencies. Returns JSON {blocks, forks, fork_outputs, logical_issues, view_issues, ok, issues:[…]} — each issue string is prefixed [LOGICAL] (audio actually broken: orphan forks, dangling fork_outputs, fork_outputs feeding nothing/a dead consumer) or [VIEW] (cable looks broken but audio OK: a fork stranded from its block). Use to verify stream-wiring health after group/ungroup/move/delete. Side-effect-free.

*No parameters required.*

---

### group_objects

Wrap the listed blocks into a new subpatch (group) in the current scope. All targets must already be in the current scope; cross-scope grouping is rejected.

Connections are preserved across grouping: a wire fully inside the group stays internal, and a wire crossing the new boundary (to a block left outside) is kept as a boundary-port connection on the new subpatch — inspect it via get_object_info on the subpatch. You do NOT need to re-issue crossing wires after grouping. (Only a wire whose far end is in a genuinely disjoint scope — neither inside the group nor an ancestor of it — is dropped.)

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `targets` | `array` | List of object ids, AI labels, or names to group. All must be in the current scope. |
| `name` | `string` | Optional display name for the new subpatch (sets ForcedName). |
| `description` | `string` | Optional description text (sets ForcedDescription). |

---

### ungroup_subpatch

Dissolve a subpatch: its children move up into the parent scope, the wrapper is removed. The subpatch must be a direct child of the current scope.

IMPORTANT: wires crossing the (former) subpatch boundary are SEVERED on ungroup, matching the human VR flow. Use disconnect_objects + connect_objects manually if you need wires to survive a round-trip.

**Parameters:**

| Parameter | Type | Description |
| --- | --- | --- |
| `identifier` | `string` | Subpatch object id, AI label, or name in the current scope. |

---
