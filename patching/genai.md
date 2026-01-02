---
title: Genrative AI in PatchWorld
description: Create assets using AI 
published: true
date: 2026-01-02T23:30:37.908Z
tags: 
editor: markdown
dateCreated: 2025-08-13T19:17:58.788Z
---

# Genie device
1. Open create tab 
2. Look for the Genie device
3. Spawn and follow the instruction on the device

# Portal
Alternatively you can use the "Gen AI" section in portal.patchxr.io
It has some extra parameters and image to 3d model options.

# Commands

The Genie device made by Dj Patchy utilizes the execute block with commands for gen ai. 
Search for Gen AI in the library and you will find it. 

Internally it uses these commnads


- **Text-to-Audio**: `gen_audio <seconds> <steps> "<prompt>"`

-   **Text-to-Model**: `gen_model "<prompt>"` 
- **Image-to-Model**:  `gen_mesh "AssetId/url"` (use the get name block to get image asset id or url)

-   **Text-to-Image**: `gen_image "<prompt>"`

-   **Text-to-Skybox**: `gen_skybox <style_id> "<prompt>"`
-   **Get Skybox Styles**: `skybox_styles`


