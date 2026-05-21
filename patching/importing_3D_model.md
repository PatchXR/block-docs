---
title: Importing 3D Models
description: Importing 3D Models
published: true
date: 2026-05-21T20:46:35.692Z
tags: assets
editor: markdown
dateCreated: 2026-05-21T20:46:35.692Z
---

# Importing 3D Models

Patchworld allows you to bring your own custom 3D creations into the game.

> [!IMPORTANT]
> Patchworld currently only supports the **`.glb`** format for 3D models. Please ensure your files are exported correctly before importing.

## How to Import a 3D Model

There are two primary ways to import your 3D models into Patchworld:

### Via PC (Portal)
1. Open your web browser and navigate to [https://portal.patchxr.io](https://portal.patchxr.io).
2. Log in and click on the **Upload** tab.
3. Drag and drop your `.glb` files into the upload area.
4. Open Patchworld, and your 3D assets will now be visible in the **My Assets** tab within your in-game library.

### Via In-Game Web Browser
1. Spawn a [Web Browser](/blocks/system/webview_browser) block in your world.
2. Navigate to any website offering 3D models and download a `.glb` file directly in VR.
3. Once downloaded, the 3D assets will automatically appear in the **My Assets** tab of your library.

---

## Making 3D Models Collidable

If you want your imported models to act as solid ground, walls, or obstacles that the player can bump into, you can make them physical and hittable.

### Step-by-Step Guide
1. **Prepare the Player**: Spawn a [Players](/blocks/players/players) block. Connect the **Local Player** Tag output to the Tag input of a [Make Physical](/blocks/motion/make_physical) block. This ensures the player is treated as a physical object in the simulation.
2. **Prepare the Model**: Connect your [Mesh](/blocks/extensions/mesh) block to the Tag input of a [Make Hittable](/blocks/motion/set_hittable) block.
3. **Block the Player**: Open the inspector (using the radial menu) on the [Make Hittable](/blocks/motion/set_hittable) block and make sure the **Block physical players** option is checked.

> [!WARNING]
> **Important Collision Rules:**
> - Player collisions will only work correctly on 3D models that **do not have animations**.
> - If a 3D model is made dynamic (moved by physics forces) via the [Make Physical](/blocks/motion/make_physical) block, its collision mesh will automatically become **convex**. This means any holes, caves, or concave shapes will be "filled in" and simplified for performance.

---

## Animations and Blendshapes

You can bring your models to life using animations and blendshapes embedded directly within your `.glb` files.

### Playing an Animation
Use the [Set Animation](/blocks/visual/set_animation) block to trigger and control skeletal animations. 
- You can blend animations in and out smoothly using the **Weight** dial.
- In the block's inspector, you can enable **Additive animation** to layer multiple animations on top of each other rather than replacing them.

### Playing a Blendshape
Use the [Set Blendshape](/blocks/visual/set_blendshape) block to drive morph targets.
- **What is a Blendshape?** Also known as a "Shape Key" (in Blender) or "Morph Target", a blendshape allows you to smoothly deform a mesh from its base shape into a new shape. They are commonly used for character facial expressions, breathing animations, or melting effects. 
- You can easily create these in Blender by adding Shape Keys in the mesh data properties, modifying the mesh in Edit Mode, and exporting the result as a `.glb`.

---

## Current Limitations

> [!NOTE]
> It is currently not possible to copy a single sub-mesh (a specific part of a larger 3D model) multiple times. If you want to duplicate a specific piece, you must copy the entire [Mesh](/blocks/extensions/mesh) block completely.
