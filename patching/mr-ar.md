---
title:   Mixed and Augmented Reality
description: 
published: true
date: 2025-08-16T10:14:35.761Z
tags: 
editor: markdown
dateCreated: 2025-08-16T10:07:28.383Z
---



This guide provides a technical overview of the Mixed Reality (MR) and Augmented Reality (AR) functionalities within Patchworld.

#### 1. Definitions

*   **Mixed Reality (MR):** Uses the headset's passthrough camera to replace the virtual skybox with a view of the physical room. Virtual objects are overlaid onto the real world.
*   **Augmented Reality (AR):** Creates virtual "windows" or portals within a virtual environment that look out into the physical room.


#### 2. Activating Mixed Reality (Passthrough)

MR is enabled by spawning specific blocks from the library.

**Location:** `Library > Visuals > Sky`

**Activation Blocks:**
*   **`Passthrough` Block:** The most direct method. Spawning this block immediately activates the passthrough view, making the virtual background transparent.
*   **`Mixed Reality` Block:** An advanced block that leverages the Quest's Room Setup data (walls, furniture, etc.). It allows for selective visibility of scanned physical objects and includes functionality for creating persistent MR anchors.

#### 3. Anchoring and Multiplayer Synchronization

**Host's Actions:**
1.  Stand in the desired center point of your physical play space.
2.  Open the **radial menu** on an empty space.
3.  Select **"Set MP Anchor Point"**.

This creates a persistent anchor tied to a scanned room, making it ideal for reopening worlds in the same layout and for co-located multiplayer. Make sure to save your world.


