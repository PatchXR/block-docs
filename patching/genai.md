---
title: Genrative AI in PatchWorld
description: Create assets using AI 
published: true
date: 2026-01-02T23:31:58.687Z
tags: 
editor: markdown
dateCreated: 2025-08-13T19:17:58.788Z
---

# Genie device
1. Open [library](/patching/library) tab  
2. Look for the Genie device (search for "Gen AI")
3. Spawn and follow the instruction on the device

# Portal
Alternatively you can use the "Gen AI" section in portal.patchxr.io


# Commands

The Genie device made by Dj Patchy utilizes the execute block with commands for gen ai. 


Internally it uses these commnads


- **Text-to-Audio**: `gen_audio <seconds> <steps> "<prompt>"`

-   **Text-to-Model**: `gen_model "<prompt>"` 
- **Image-to-Model**:  `gen_mesh "AssetId/url"` (use the get name block to get image asset id or url)

-   **Text-to-Image**: `gen_image "<prompt>"`

-   **Text-to-Skybox**: `gen_skybox <style_id> "<prompt>"`
-   **Get Skybox Styles**: `skybox_styles`


