---
title: FAQ
description: Frequently asked questions
published: true
date: 2025-09-18T10:13:19.003Z
tags: 
editor: markdown
dateCreated: 2025-08-13T15:34:54.206Z
---

## **How do I access the advanced building tools "Blocks"?**

Open the main menu (aka hub), choose "create tab", select "Blocks", a prompt will show up, select to open the beta features. 
The blocks will be now availabe. [Beta mode is not the same as beta builds](/patching/beta). 

---

## **Q: How do I import my own samples, 3D models (meshes), or images into Patchworld?**


**A:** The recommended method is to use the PatchXR Web Portal: **https://portal.patchxr.io/**.
via the "Upload" menu. [Check this](/import-files)

---

## **Q: My created worlds have disappeared, or the "My Worlds" tab is empty. How do I get them back?**


**A:** This is a known issue, often caused by a crash or a local data corruption. The most effective solution is to **reinstall the Patchworld app**. Your worlds are saved to the cloud, so they should reappear after you reinstall and log in. Another method that has worked for users is to connect the Quest to a PC, use SideQuest, and go to `Apps -> PatchXR -> Settings -> Clear App Data`.

---

## **Q: How can I connect Patchworld to Ableton Live or use it as a MIDI/OSC controller?**


**A:** Patchworld supports this primarily through OSC over your local Wi-Fi network.
1.  **Ableton Live:** You need the `PatchWorld OSC Bridge` Max for Live device. Your PC/Mac running Ableton and your Quest headset must be on the same local network. The device in Ableton will scan for your headset's IP address to establish a connection.
2.  **MIDI Companion App:** The team has also developed a "Patch Companion App" for Windows and Mac that creates a virtual MIDI port, making it easier to connect to any DAW without complex OSC setup.
3.  **General OSC:** You can use the `msg in` and `msg out` blocks for custom OSC messaging with software like TouchOSC or Pure Data. You will need to use `execute` blocks to set the `remote_ip` and ports (`port_in`, `port_out`) correctly.

see: [external-connections](/patching/external-connections)

---

## **Q: How can I record my music or performances from Patchworld? Can I export stems?**


**A:** There is no direct "Export Audio" feature. There a few methods, choose whats best for your flow:
1.  **Screen Recording:** The easiest way is to use the Quest's built-in screen recording feature. This captures both video and audio of your performance. You can then transfer the video file to a computer and extract the audio.
2.  **Field Recorder Device:**  you can use the `Field Recorder` device. You will need to route the audio stream from your instruments into the recorder's input. 
3. **Listener Blocks** they capture all audio around them from the world. 
4. For full live audio, best way is connecting physical output from headphone jack to audio interface/recorder
5. Using [scrcpy](/dev/scrcpy) on computer, recording audio/video using obs
6. You can also capture avatar performance and save it as a world. see [Ghost Recordings](/patching/ghosts)

When recording to bubbles, your audio will be saved as an Asset and will be available in your library. 
You can then download in from your library on [the web portal](/patching/patch-web-portal)
 
---

## **Q: I'm experiencing high audio latency, especially with the microphone. Is there a fix?**


**A:** This is a known limitation, partly due to the Quest's native audio drivers.
*   **Microphone:** The headset itself has some unavoidable latency. The `bubble maker` device has some built-in compensation to work better with loopers.
*   **General Latency:** Using **Bluetooth headphones** is strongly discouraged as it introduces significant audio delay. Wired headphones or the built-in speakers provide the best experience. For performance-critical playing (like drumming), you can go into the settings and lower the audio buffer size, but be aware this can cause crackling or issues with vocal recording.

---

## **Q: How do I delete objects I've spawned in my world?**


**A:** Use the radial menu. Point at the object you want to delete and press and hold the **A button** (right controller) or **X button** (left controller). A radial menu will appear. Move your controller to highlight the "Remove" option and then select either "Cut" (to place it on your clipboard) or "Delete" (to remove it permanently).

## **Q: What is BETA mode VS Beta Builds?**


**A:** 
Beta mode is a mode in the app. 
Beta builds are pre-released versions of the app. [beta](/patching/beta)

---

## **Q: What is the difference between a Jolt (thin wire) and a Stream (thick wire)?**

**A:** These are the two fundamental signal types in Patchworld.
*   **Jolt (thin, colorful wire):** Represents an event. It sends a single number or a trigger at a specific moment, much like a "bang" or a MIDI note in other patching environments. Jolts are used to trigger actions (like playing a note), change a value, or send control signals. The order in which you connect jolt wires matters, as they fire sequentially.
*   **Stream (thick, black wire):** Represents a continuous flow of data, like an audio signal or an LFO. It sends thousands of values per second. Streams are used for audio signals that you connect to speakers, effects, or analysis blocks.
*   **Converting:** You can convert a Stream to a Jolt using a `stoe` block, which samples the stream's value at a regular rate.

---

## **Q: How do I save a creation (like an instrument) so I can use it in other worlds?**

**A:** You can save a group of blocks as a "Device."
1.  In Edit Mode, use the **Grip button** to activate the selection sphere and select all the blocks that make up your creation.
2.  Point at the selection and open the radial menu (**A/X button**).
3.  Choose **Inspect**.
4.  In the menu that appears, select **Make Device**.
5.  Give your device a name.
6.  Your new device will be saved to your personal library under the **Devices -> My Devices** tab, and you can now spawn it in any of your worlds.

---

## **Q: How can I align objects precisely? Snapping seems difficult.**

**A:** Aligning objects can be tricky, but there are tools to help.
*   **Ruler Block:** The `Ruler` block is the primary tool for alignment. You can spawn it from the library, lock it in place, and use it as a grid to snap your objects to.
*   **Landmark Block:** When you group objects to create a device, its snapping point can feel random. To fix this, place a `Landmark` block *inside* the group before you save it as a device. The Landmark's position and orientation will define the new anchor point for the entire group, making it much easier to align.
*   **Set Position Block:** For programmatic control, you can use the `set_position` block to move an object to exact coordinates.
* using the grid

---

## **Q: Does Patchworld have multiplayer? How do I start or join a session?**

**A:** Yes, multiplayer is a core feature.
*   **Starting a Session:** Go to the info page of a world you have saved. You will see a "Start Live Session" button. This makes your world visible to other users.
*   **Joining a Session:** In the main hub or landing area, there is a "Live Sessions" or "Rooms" menu. This will show all currently active public sessions that you can join.
*   **Private Sessions:** Once you start a live session, you can go into the session menu and set it to private, so only users you invite can join.

---

## **Q: How do I make something happen automatically when a world loads (like a 'loadbang')?**

**A:** There are two main ways to do this:
1.  **OnLoad Wireless Jolt:** Spawn a `Wireless In Jolt` block and, in its Inspector menu, set the channel name to exactly `onload`. This block will automatically fire a single jolt whenever the world is loaded, which you can use to trigger music, animations, or set initial states.
2.  **Anchor Block:** Spawn an `Anchor` block. In its Inspector menu, you can check an option for it to trigger automatically on load. This is primarily used to set the player's starting position and orientation when they enter the world.

---

## **Q: What is the difference between Play Mode and Edit Mode (sometimes called 'Show Hidden')?**

**A:** These two modes are essential for creating and experiencing worlds.
*   **Edit Mode (Show Hidden):** This is the building mode. You can see all blocks (even those intended to be hidden), move them around, and make connections. Physics are typically disabled in this mode so objects don't fly away while you're working on them.
*   **Play Mode (Hide Hidden):** This is the performance or experience mode. Any blocks set to be hidden will become invisible and non-interactive. Physics are enabled, sequencers start playing, and the world functions as intended for a visitor. You switch between modes to build and then test your creations.

---

## **Q: Can I use Patchworld on PCVR with headsets like Valve Index or HTC Vive?**


**A:** Yes, there is a PCVR version of Patchworld available on Viveport, and the team provides beta PC builds. However, the primary development focus is on the standalone Quest platform. As a result, support for non-Quest controllers (like the Index Knuckles) has been inconsistent and is a known issue. The PCVR version may be less stable and is best used for high-performance tasks like video recording.

---

## **Q: Can I change my avatar?**

**A:** Yes. There is a world called **Avatar Studio** (or similar) accessible from the hub where you can customize your appearance. Patchworld supports importing your **Ready Player Me** avatar for a personalized look, or you can switch back to the default wireframe-style avatars. You can also attach any object or mesh to your avatar's head or hands to create unique headwear or accessories.
