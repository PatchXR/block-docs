---
title: Manage your content
description: 
published: true
date: 2026-01-02T23:09:51.125Z
tags: 
editor: markdown
dateCreated: 2025-08-15T18:48:02.663Z
---

The two main tools at your disposal are the **in-app Hub and Library** and the external **Patch Portal** website.

---

#### The Core of Your Creations: Worlds and Patches

Your worlds are the canvases where everything happens. Understanding how they are saved and managed is fundamental.

**Saving Your Work:**
*   **Save vs. Save Copy:** When working on a world you own, you can use the **Save** button to update it. If you are in a world created by someone else, or want to create a version of your own world, use the menu option **Save Copy**. 
*   **Cloud Sync:** When you save, you'll often see a "Uploading to the Cloud" message. It's crucial to let this process complete before saving again or exiting, as interrupting it can sometimes cause issues. If you are offline, saves are local and instant.
*   **Backups:** Patchworld automatically saves previous versions of your world. If you accidentally delete something or a save gets corrupted, navigate to the world's info page and look for a **Backups** or **Version History** tab to restore an older version.

**Publishing and Thumbnails:**
*   **Publishing:** To make a world visible to everyone on your public profile, use the **Publish** button on its info page.
> Notice that when saving a published patch, this saves a private draft version. Use "Update Published" to publish latest draft.
*   **World Thumbnails:** To create a custom thumbnail for your world:
    1.  Inside your world, spawn a **snapcam** block.
    2.  Take a picture with it.
    3.  Use the radial menu on the resulting photo, go to **Inspect**, and select "Use as World Cover."
    4.  Alternatively, you can upload a thumbnail image directly on the [Patch Portal](/patching/patch-web-portal).

---

#### The Patch Portal

The ([**Patch Portal**](/patching/patch-web-portal)) is the central hub for uploading and managing your personal assets. You log in with your Meta account, and anything you upload will become available in your in-app library.

**Importing Assets:**
[import-files](/import-files)

**Syncing Your Library:**
After uploading assets to the Portal, refresh "Assets > All My assets" in the library. 

---

#### Building Your Arsenal: Creating and Saving Devices

One of Patchworld's most powerful features is the ability to group blocks into a custom "Device" that you can save and reuse across all your worlds.

**The Process:**
1.  **Build Your Contraption:** Create your instrument, effect, or tool using blocks.
2.  **Select Everything:** Use the **grip button** to activate the selection sphere. You can resize the sphere with the joystick to easily select all the components.
3.  **Group and Save:**
    *   Open the radial menu and select **Group**.
    *   Open the radial menu again on the newly created group.
    *   Go to **Inspect**. At the bottom of the Inspector panel, you will find a **"Make Device"** button.
    *   Give your device a name and save it.
4.  **Find Your Device:** Your new creation will now be available in your library under **Devices > My Devices**.

---

#### Capturing Performances: Managing Ghosts

Ghost recordings are saved as part of the world they were recorded in. If you want to share a performance, you must share the world itself.

*   **Recording:** Use the **Ghost Recorder**, **Avatar Looper**, or **Ghost Loop Station** to record your movements and voice.
*   **Timeline:** For longer recordings, remember to adjust the timeline length in the Recording menu to ensure your full performance is captured.
*   **Synchronization:** To ensure multiple ghosts start at the same time, trigger their "Play" inputs simultaneously, often with a single `onload` jolt.

---

#### Common Issues and Troubleshooting

*   **"My Worlds / My Devices list is empty!"**
    *   This is a known issue that can sometimes occur if the app crashes or a local file gets corrupted. The most reliable fix is to **uninstall and reinstall Patchworld**. Your cloud-saved worlds and portal assets will be safe and will re-sync after you log back in.

*   **Saving Fails or Gets Stuck on "Uploading to the cloud"**
    *   This is often related to a slow or unstable internet connection. First, be patient, as large worlds can take a few minutes. If it remains stuck, the best workaround is to use **"Save Copy"** to create a new version of the world. As a last resort, select all objects in your world, copy them to the clipboard, create a new empty world, and paste them in.

*   **Downloading Assets from the Portal gives a `.dat` file**
    *   If you download a sample and it saves as a `.dat` file, simply **rename the file extension to `.wav`**. It should then play correctly.