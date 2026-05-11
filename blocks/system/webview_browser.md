# Web Browser

**Category**: ⚙️ System

![webview_browser thumbnail](https://portal.patchxr.io/block-thumbnails/webview_browser.png)

## Description

Embeds a web browser into the VR environment with interactive navigation controls.

Displays web pages on a resizable 3D canvas. Type a URL into the text input or use the inspector to navigate. Supports standard browser actions (back/forward/refresh, zoom, download), virtual keyboard input, and configurable resolution. Audio from web content plays directly through the system (it does not route through Patchworld's synthesis engine).

## Inputs, Outputs and Parts

### Inputs

| Name | Type | Description |
|------|------|-------------|
| Back | Jolt Input | Navigate to the previous page in browser history. |
| Forward | Jolt Input | Navigate to the next page in browser history. |
| Refresh | Jolt Input | Reload the current page. |
| Enable Audio | Jolt Input with Dial | Sets the volume of the web content (0 = mute, 1 = full). Audio bypasses Patchworld's synthesis engine. |
| Zoom | Jolt Input with Dial | Sets the page zoom level. |
| Download | Jolt Input | Download a preview of the current page. |
| Open Keyboard | Jolt Input | Opens the virtual keyboard for typing into the currently focused page field. |
| URL | Text Input | Text input to enter a web address. When edited, the browser navigates to the new URL. |
| Send Key Down | Jolt Input | Simulates pressing the key(s) configured via the 'Keyboard Key' Tag input. |
| Send Key Up | Jolt Input | Simulates releasing the key(s) configured via the 'Keyboard Key' Tag input. |
| Keyboard Key | Tag Input | Connect text blocks here whose contents are the key names to emulate (e.g. 'Enter', 'Escape', 'ArrowUp'). Trigger 'Send Key Down'/'Send Key Up' to fire them. See JavaScript's Keyboard_event_key_values for the full list of valid names. |

### Others

| Name | Type | Description |
|------|------|-------------|
| Resize | Draggable part | Drag this handle to resize the browser window (snaps to the layer grid). |
| Canvas | Interactible | The web page display area. Interact directly with the page (click links, scroll, type into fields). |

## Inspector Controls

| Name | Type | Description |
|------|------|-------------|
| Navigate to URL | text_input | Type a URL here and press Enter or click Go to load it. |
| Go | button | Loads the URL currently typed in 'Navigate to URL'. |
| Hide text input in play mode | checkbox | When enabled, the URL text input is hidden while in play mode. Serialization keyword: hideUrlInputInPlay |
| Hide resize handle in play mode | checkbox | When enabled, the resize handle is hidden while in play mode. Serialization keyword: hideResizeHandleInPlay |
| Resolution | dropdown | Internal rendering resolution of the page (taller = sharper text but more GPU). Serialization keyword: res (0=800, 1=1200, 2=1600, 3=2200) |
| Drag Action | dropdown | Choose what dragging on the page does: 'Move Items' grabs draggable items (default), 'Scroll' scrolls the page. Serialization keyword: dts (true = Scroll, false = Move Items) |
| Lock Size | checkbox | When enabled, the resize handle is locked so the browser size cannot be changed by dragging. |
| Edit text from outside | checkbox | Allows the URL text input to be edited from outside its parent group. Serialization keyword: Etfo |

## Related Blocks

- [image](/blocks/visual/image)
- [txt](/blocks/visual/txt)
- [join_apply_text](/blocks/system/join_apply_text)

---