---
title:   Mixed and Augmented Reality
description: 
published: true
date: 2026-05-11T15:45:08.410Z
tags: 
editor: markdown
dateCreated: 2025-08-16T10:07:28.383Z
---

# Mixed Reality & Augmented Reality

Patchworld supports Mixed Reality (MR) and Augmented Reality (AR) on headsets equipped with passthrough cameras (Meta Quest, Pico, HTC Vive XR). This page covers the blocks that enable these features, how to combine them, and how multiple players sharing the same physical room can synchronize their virtual space.

---

## Definitions

*   **Mixed Reality (MR):** The headset's passthrough camera replaces the virtual skybox with a live view of the physical room. Virtual objects are overlaid onto the real world. The Quest Room Setup data (walls, furniture, etc.) can optionally be used to selectively reveal or occlude real-world surfaces.
*   **Augmented Reality (AR):** Virtual "windows" or portals are placed inside a virtual environment that look out into the physical room — the inverse of MR.
*   **Passthrough:** The raw camera feed from the headset. Passthrough is the underlying technology that both MR and AR features rely on.

---

## Blocks overview

All MR/AR blocks live in **Library > Visuals > Sky**.

| Block | Thumbnail | Role |
|---| --- |---|
| [Passthrough](/blocks/visual/passthrough) | ![Passthrough thumbnail](https://portal.patchxr.io/block-thumbnails/passthrough.png =60x60) | Simplest way to enable passthrough. Spawning it immediately makes the virtual background transparent. Includes an opacity dial. |
| [Mixed Reality](/blocks/visual/mixed_reality) | ![Mixed Reality thumbnail](https://portal.patchxr.io/block-thumbnails/mixed_reality.png =60x60) | Advanced passthrough that uses Quest Room Setup. Toggles per-furniture-type visibility (ground, walls, ceiling, windows, doors, desk, couch, others). Includes opacity, outline display, and co-located multiplayer sync. |
| [AR Window](/blocks/visual/ar_window) | ![AR Window thumbnail](https://portal.patchxr.io/block-thumbnails/ar_window.png =60x60) | A resizable plane that cuts a hole of real-world passthrough into the virtual scene. Drag the corner handle to resize. |
| [Vr Window](/blocks/visual/vr_window) | ![Vr Window thumbnail](https://portal.patchxr.io/block-thumbnails/vr_window.png =60x60) | The inverse of AR Window: while passthrough is active, the area covered by this plane reveals the virtual world instead of the real one. Pair with [Passthrough](/blocks/visual/passthrough) or [Mixed Reality](/blocks/visual/mixed_reality). |
| [Magic Window](/blocks/visual/magic_window) | ![Magic Window thumbnail](https://portal.patchxr.io/block-thumbnails/magic_window.png =60x60) | Snaps to detected walls on world load (when paired with [Mixed Reality](/blocks/visual/mixed_reality)). Reveals the virtual scene through real walls. Also acts as a laser-pointer canvas with coordinate, hover, and trigger outputs — ideal for placing UIs and interactive panels on real-world surfaces. |
| [Magic Spotlight](/blocks/visual/magic_spotlight) | ![Magic Spotlight thumbnail](https://portal.patchxr.io/block-thumbnails/magic_spotlight.png =60x60) | A spotlight beam that reveals passthrough wherever it shines. Toggle on/off and modulate intensity via jolt input. Great for theatrical effects mixing virtual content with the physical room. |

---

## Activating Passthrough (Simple)

Spawn the [Passthrough](/blocks/visual/passthrough) block. The virtual background immediately becomes transparent and shows your physical room.

**Inspector options:**

*   **Show handle in playmode** — keep the grab handle visible so the block can be repositioned while playing.
*   **Always straight** — constrain the block to stay vertically aligned.
*   **Display Background** — toggle the virtual skybox behind the passthrough feed.

The **Opacity** dial (0–1) on the block fades between fully virtual (0) and fully real (1).

---

## Activating Mixed Reality (Advanced)

Spawn the [Mixed Reality](/blocks/visual/mixed_reality) block. This enables passthrough *and* leverages the headset's **Room Setup** data (the scan of your physical room) so the system knows where walls, floor, ceiling, furniture, etc. are located.

**Furniture toggles on the block face:**

Each toggle enables/disables visibility for a furniture category. All are on by default:

*   Ground · Walls · Ceiling · Windows · Doors · Desk · Couch · Others

Every toggle also has a **jolt input** so you can wire other blocks to control furniture visibility programmatically.

**Inspector options:**

*   **Show outlines** — render outlines around detected real-world surfaces so the player can see the limits of the room.
*   **Sync local MP** — enable co-located multiplayer synchronization (see below).
*   **Debug mode** — show developer debug output for the MR system.

---

## AR & VR Windows

Use these blocks to create portals between the virtual and real worlds:

### AR Window

The [AR Window](/blocks/visual/ar_window) punches a rectangular hole of passthrough into the virtual scene. The player can peek at their physical surroundings without leaving VR.

*   Drag the **Resize Handle** (corner) to change the window size.
*   Position and rotate freely.
*   Works without requiring the [Mixed Reality](/blocks/visual/mixed_reality) block — it enables passthrough on its own.

### VR Window

The [Vr Window](/blocks/visual/vr_window) is the opposite: when passthrough is active, the area behind this plane shows the virtual world instead of the real one. It acts as a stencil.

*   Requires [Passthrough](/blocks/visual/passthrough) or [Mixed Reality](/blocks/visual/mixed_reality) to be active.
*   Drag the **Resize Handle** (corner) to change size.
*   Combine multiple VR Windows to create framed VR portals into your physical room.

---

## Magic Window & Magic Spotlight

### Magic Window

The [Magic Window](/blocks/visual/magic_window) is designed for mixed reality room setups. When **Snap On Load** is enabled in the inspector, every Magic Window in the world automatically attaches itself to a detected wall when the world loads (requires [Mixed Reality](/blocks/visual/mixed_reality)).

Beyond revealing the virtual scene through real walls, it also works as a **laser-pointer canvas**:

*   **x** / **y** outputs — normalized (0–1) coordinates of where the controller is pointing on the canvas.
*   **hover** output — 1 when pointing at the canvas, 0 otherwise.
*   **trigger** output — 1 while the trigger is pressed on the canvas.
*   **hit** output — emits the impact speed when a marble or controller physically hits the window.

**Inspector options:**

*   **Distance limit** — maximum laser interaction range (meters).
*   **Resizable** — allow the corner handle to resize the canvas.
*   **Snap On Load** — auto-snap to a detected wall when the world finishes loading.

This makes [Magic Window](/blocks/visual/magic_window) ideal for placing interactive UIs, control panels, or musical instruments directly on your real-world walls.

### Magic Spotlight

The [Magic Spotlight](/blocks/visual/magic_spotlight) projects a cone of passthrough wherever its beam points. Use it together with [Mixed Reality](/blocks/visual/mixed_reality) to dynamically punch a beam of real world into the virtual scene.

*   **On/Off toggle** — enable or disable the spotlight.
*   **Intensity jolt input** — modulate how brightly the spotlight reveals the real world.
*   **Show outlines** (inspector) — shared outline setting for detected furniture.

---

## Anchoring & Co-Located Multiplayer Synchronization

*(Meta Quest Standalone only)*

When multiple players wearing Quest headsets are physically in the **same room**, Patchworld can synchronize their virtual coordinate systems so that every player sees virtual objects at the same physical location. This is key for sharing augmented reality experiences in a shared space — each player sees blocks placed on the same table, stuck on the same wall, or floating in the same spot in the room.

### How it works

1.  **Spatial Anchor** — each device creates or loads a persistent Meta spatial anchor tied to the physical room. This anchor serves as a shared origin point between all players.
2.  **Anchor sharing** — when a multiplayer session is active and "Sync local MP" is enabled, the anchor is shared via Meta's cloud anchor system. The player who joined the session **first** (lowest join ID) becomes the reference — other players' coordinate systems are aligned to that player's anchor.
3.  **Automatic teleport** — once anchors are aligned, the VR base is silently moved so that the anchor positions match. From that point on, every player's virtual world lines up with the physical room.

### Setting up a co-located MR experience

1.  **Room Setup** — make sure every Quest in the room has completed Meta's Room Setup for the same physical space.
2.  **Spawn the block** — add a [Mixed Reality](/blocks/visual/mixed_reality) block to your world.
3.  **Enable sync** — open the inspector on the Mixed Reality block and check **Sync local MP**. This can also be enabled for all players via script using `SetSyncPhysicalSpace(true)`.
4.  **Set the MR anchor point** (optional, for manual fine-tuning):
    *   Stand in the desired center point of your play space.
    *   Open the **radial menu** on an empty space.
    *   Select **"Set MP Anchor Point"**.
5.  **Save the world** — the anchor is persisted with the world data. When the world is reopened in the same room, the anchor is automatically reloaded.

### What happens behind the scenes

*   When a player joins a session with sync enabled, all players broadcast their spatial anchor UUIDs.
*   The system picks the anchor from the player who joined earliest (ensuring consistency).
*   Each device attempts to localize the shared anchor in its own physical space — if the rooms match, the coordinate systems align.
*   Avatars of players sharing the same physical space are automatically hidden to avoid visual clutter (you see them in real life already).
*   A toast message notifies you when other players in the same physical space are detected.

### Debug tools

When **Debug mode** is enabled on the [Mixed Reality](/blocks/visual/mixed_reality) block, additional options appear in the **World Inspector** (the inspector opened on empty space):

*   **Set as MR position** — manually place the reference anchor at your current position.
*   **Move to MR position** — teleport yourself to the current anchor position.
*   **Sync MR position** — toggle multiplayer position sync (same as "Sync local MP" on the block).
*   **Clear user anchor in player pref** — remove the locally cached anchor so a fresh one is created next time.

---

## Tips

*   Start with [Passthrough](/blocks/visual/passthrough) for a quick MR setup. Upgrade to [Mixed Reality](/blocks/visual/mixed_reality) when you need room-aware features (furniture visibility, wall snapping, co-located multiplayer).
*   Combine [Magic Window](/blocks/visual/magic_window) with UIs, synthesizers, or game elements to build interactive surfaces that live on your real walls.
*   Use [AR Window](/blocks/visual/ar_window) in otherwise fully virtual worlds to let players keep an eye on their physical surroundings (safety, awareness).
*   Use multiple [Vr Window](/blocks/visual/vr_window) blocks with [Passthrough](/blocks/visual/passthrough) to create "framed" virtual paintings or portals hanging in your real room.
*   Use [Magic Spotlight](/blocks/visual/magic_spotlight) for theatrical reveals — sweep a beam across the room to dynamically expose the real world.
*   For co-located multiplayer, **all players must be in the same Meta Quest multiplayer room** and have completed Room Setup for the same physical space. The anchor system relies on Meta's shared spatial anchors.