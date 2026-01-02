---
title: Assets
description: What are assets ?
published: true
date: 2025-08-14T01:57:48.329Z
tags: 
editor: markdown
dateCreated: 2025-08-13T18:47:17.473Z
---


Everything from sounds and visuals to 3D models and custom devices.
Created in the app or imported.
The create tab (aka library) is the place to find the assets available to spawn.

> **Looking to add your own assets?** Check out our guide on [importing files](/import-files).
{.is-info}

# Available Asset Types

Patchworld supports five main asset types, each with its own unique properties and inspector options:

## 🔊 Audio
- Audio files spawn as **bubble blocks** that contain your sound.
- Bubbles can only play mono signals at the moment, so when importing multi channel audio only the first channel will play. This will probably be improved soon, but for the moment the bast way is to split the channels before importing to PatchWorld.

## 🖼️ Images & GIFs
- Static images and animated GIFs appear as **image blocks**, displaying your visual content directly in your world.
- Images can also be spawned as 360 images
- **Supported formats:** `.jpg`, `.jpeg`, `.png`, `.gif`

## 🎬 Video
- Video files spawn with a built-in **video player block**, complete with playback controls.
- **Supported formats:** `.mp4`, `.avi`, `.mov`

## 🎨 3D Models
- 3D models appear as **model blocks** .
- **Supported format:** `.glb`

## ⚙️ Devices
- Devices are special assets created by grouping blocks together, then turning them into a device. These are reusable, sharable patches.


> **Learn more:** See our guide on [Groups and Devices](/patching/groups-and-devices) to create your own custom devices.

> **💡 Did you know?** You can use [generative AI](/patching/genai) to create assets directly in Patchworld! Generate sounds, 3d models, 360 images and more without leaving the app.
{.is-success} 


## Publishing Assets 
You can publish your assets by selecting it in the create tab, then clicking the "eye" icon on the bottom right.
This will allow other users to see this asset as published.
To see assets from other users, navigate to their profile then click "Published Assets", this will open the create tab showing their published assets.

## Featured Assets
PatchWorld mods can set certain assets to be Featured, meaning these will show up in the public library (create tab) for all of the users.

## Selling Assets
A published/featured asset, that has a price, will be spawnable to users that purchase the asset.
Set the price to your assets by connecting a purchase block to them and inspecting the purchase block.
Or via the patch web portal portal.patchxr.io
