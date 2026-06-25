---
title: Web Bridge - Make your own Block
description: 
published: true
date: 2026-06-25T23:52:05.060Z
tags: 
editor: markdown
dateCreated: 2026-06-25T23:52:05.060Z
---

# Web Bridge

The **Web Bridge** allows creators to build custom web user interfaces (HTML/CSS/JavaScript) and embed them directly into their VR worlds. By pairing a [Web Bridge](/blocks/system/web_bridge) block with a [Web Browser](/blocks/system/webview_browser) block, your JavaScript code can communicate bidirectionally with Patchworld's core engine. This unlocks limitless possibilities for designing custom synth panels, game HUDs, interactive leaderboards, and complex gameplay logic.

## Video Walkthrough

![Patchworld Web Bridge Overview](https://youtu.be/BPgv_opqNzI)

> **Note:** This tutorial demonstrates the Web Bridge block in action inside VR and provides a quick introductory overview of the GitHub hosting setup. *(If the player does not render above, [watch directly on YouTube](https://youtu.be/BPgv_opqNzI)).*

---

## Core Blocks Overview

| Block | Thumbnail | Description |
|---|---|---|
| [Web Bridge](/blocks/system/web_bridge) | ![Web Bridge thumbnail](https://portal.patchxr.io/block-thumbnails/web_bridge.png =60x60) | The physical interface block that bridges C# engine events and JavaScript promises. |
| [Web Browser](/blocks/system/webview_browser) | ![Web Browser thumbnail](https://portal.patchxr.io/block-thumbnails/webview_browser.png =60x60) | The 3D canvas block displaying your live HTML/JS web application. |

---

## Getting Started (Quick Setup)

You don't need complex server infrastructure to host your own VR web interfaces. You can host them automatically and for free using **GitHub Pages**.

### 1. Fork the UI Template
Start by exploring and forking the official template repository:
*   **Template Repository:** [Patchworld WebBridge Template](https://github.com/PatchXR/Patchworld-WebBridge-Template)
*   **Live Preview:** [View the Live UI Preview](https://patchxr.github.io/Patchworld-WebBridge-Template/)
*   **Video Tutorial:** [Watch the Video Overview](https://youtu.be/BPgv_opqNzI)

### 2. Enable GitHub Pages
1.  In your forked GitHub repository, navigate to **Settings > Pages**.
2.  Under **Source**, choose **Deploy from a branch**.
3.  Select the `main` (or `master`) branch and `/ (root)` folder, then click **Save**.
4.  Within a few minutes, GitHub generates your live web address (e.g., `https://your-username.github.io/Patchworld-WebBridge-Template/`).

### 3. Connect in Patchworld VR
1.  Spawn a [Web Browser](/blocks/system/webview_browser) block and paste your live GitHub Pages URL into its address field. *(Tip: For local testing without internet hosting, place your files in `StreamingAssets` and use `file://PathToYour/index.html`).*
2.  Spawn a [Web Bridge](/blocks/system/web_bridge) block.
3.  Click and drag a Tag connection from the **Web Browser** Tag Input on the bridge block directly to your browser block.

---

## Communication Capabilities

Once connected, `patchworld-bridge.js` exposes a rich asynchronous API (`window.PatchWorld`) to interact with your VR environment.

### 1. Physical & Cable I/O
You can patch physical cables into the Web Bridge block in VR to interact with scene signals:
*   **Jolt In A / B:** Incoming physical jolt pulses trigger `PatchWorld.onInterfaceInputJoltA(value)` or `B(value)` in JavaScript.
*   **Jolt Out A / B:** Emit physical jolt pulses from the block into scene wires using `await PatchWorld.interfaceSendJoltA(value)`.
*   **Text Messages:** Receive strings via `onInterfaceMessageIn(txt)` or output text to scene displays using `await PatchWorld.interfaceMessageOut(txt)`.
*   **Block References:** Plug target objects into `Block Ref In` to pass their hierarchical `fullId` and `partId` into JavaScript.

### 2. Wireless Event Channels (Wifi Jolts)
Broadcast and receive instant event pulses anywhere in the room without running cables:
```javascript
// Broadcast a wireless jolt across the room
await PatchWorld.sendWirelessJolt("synth_trigger", 1.0);

// Subscribe to incoming wireless channels
PatchWorld.subscribeWifi("synth_trigger");
PatchWorld.onWifiJolt = (channel, value) => {
    console.log(`Trigger received on ${channel}: ${value}`);
};
```

### 3. Reactive Variable System
Attach dynamic gameplay variables (such as `Score`, `Health`, or `Vibz`) to scene objects. The bridge maintains an optimized local cache in JavaScript to ensure instant reads without framerate stuttering:
```javascript
// Subscribe to live gameplay variables
PatchWorld.subscribeVariable("score");

// Instant synchronous read from local cache
let currentScore = PatchWorld.getVariable("score", playerFullId);

// Asynchronously modify variables on scene objects
await PatchWorld.setVariable("score", playerFullId, currentScore + 10);
```

### 4. Console Commands & Cloud Persistence
*   **Engine Console Commands:** Script engine operations or trigger AI commands dynamically:
    ```javascript
    await runCommand("SetTimeScale", 0.5);
    await runCommand("ToasterMessage", "Checkpoint reached!");
    ```
*   **Online Cloud Storage:** Save persistent player progress or world states directly to PatchXR backend servers:
    ```javascript
    await runCommand("PostValue", "player_level", 5);
    let savedLevel = await runCommand("FetchValue", "player_level");
    ```
*   **REST Server Queries:** Query public asset metadata and player profile details directly from WebView:
    ```javascript
    const profile = await PatchWorld.fetchUserProfile("user_12345");
    ```

---

## Vibe Coding with AI

You can iterate and customize your Web Bridge UI rapidly without installing local development tools by using AI web IDEs like **Bolt.new**.
1.  Generate a GitHub Fine-grained Personal Access Token with **Read and write** access to **Contents**.
2.  Provide Bolt.new with your forked repository URL and your access token.
3.  Prompt the AI with natural language instructions (e.g., *"Switch the layout to a dark futuristic glassmorphism theme and add a glowing master volume fader"*).
4.  Bolt commits changes directly to GitHub, automatically rebuilding your live VR UI via GitHub Pages!
