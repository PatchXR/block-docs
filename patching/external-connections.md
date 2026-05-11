---
title: External Connections
description: Midi and OSC
published: true
date: 2026-05-11T15:51:51.118Z
tags: 
editor: markdown
dateCreated: 2025-08-15T15:55:49.593Z
---

Connecting Patchworld to external devices and software like DAWs (Digital Audio Workstations) and MIDI controllers opens up a world of possibilities for live performance, advanced sequencing, and integrating physical hardware into your VR creations. This guide covers the primary methods discussed and developed by the PatchXR team and its community.

There are two main protocols for external connection:
1.  **MIDI over Network:** The recommended and more streamlined method for connecting to DAWs like Ableton Live, using a companion app.
2.  **Open Sound Control (OSC):** A more flexible but manual protocol for custom setups, controlling hardware, or connecting to software that doesn't support the companion app.

---

## Method 1: MIDI over Network (Recommended for DAWs)

This method uses the official **Patchworld Companion App** to create a stable bridge between your headset and your computer.

### Prerequisites

*   A Windows or Mac computer on the same local network as your headset.
*   A DAW like Ableton Live.
*   **For Windows:** [loopMIDI](https://www.tobias-erichsen.de/software/loopmidi.html) to create virtual MIDI ports.
*   **For Mac:** The built-in **IAC Driver**.

### Step-by-Step Guide

#### 1. Setup Virtual MIDI Ports

**On Windows:**
1.  Install and run `loopMIDI`.
2.  Create at least two new virtual MIDI ports by typing a name and clicking the `+` button. Name them something clear, like `PatchIn` and `PatchOut`.

**On macOS:**
1.  Open the **Audio MIDI Setup** application (found in `Applications/Utilities`).
2.  Go to `Window > Show MIDI Studio`.
3.  Double-click on the **IAC Driver** icon.
4.  Ensure the "Device is online" checkbox is ticked.
5.  In the "Ports" section, create at least two ports, e.g., `Bus 1` and `Bus 2`.

#### 2. Configure the Patchworld Companion App

1.  **Important:** Launch Patchworld on your headset **first**.
2.  Open the Patchworld Companion App on your computer ([Download if needed](/Downloads))
3.  The app should automatically detect your headset's IP address. Select it from the dropdown.
4.  Select your newly created virtual MIDI ports for both **Input** and **Output**. For example, select `PatchIn` for input and `PatchOut` for output.

#### 3. Configure Your DAW (Ableton Live Example)
1.  Go to `Preferences > Link / Tempo / MIDI`.
2.  In the MIDI section, find your virtual ports (`PatchIn`/`PatchOut` or `IAC Bus 1`/`IAC Bus 2`).
3.  Enable **Track** and **Remote** for both the input and output ports.

#### 4. Setup in Patchworld

Use the dedicated MIDI blocks found in the **Connectors** category of the Library:

| Block | Thumbnail | Description |
|---|---|---|
| [Midi Keys](/blocks/connectors/midi_keys) | ![Midi Keys thumbnail](https://portal.patchxr.io/block-thumbnails/midi_keys.png =60x60) | Send/receive polyphonic note messages. |
| [Midi CC](/blocks/connectors/midi_control_change) | ![Midi CC thumbnail](https://portal.patchxr.io/block-thumbnails/midi_control_change.png =60x60) | Send/receive Control Change messages. Set the CC number in the Inspector. |
| [Midi Key](/blocks/connectors/midi_key) | ![Midi Key thumbnail](https://portal.patchxr.io/block-thumbnails/midi_key.png =60x60) | Send/receive a single, specific MIDI note. |

You can now send MIDI from your DAW to Patchworld instruments or send signals from Patchworld to control your DAW.

---

## Method 2: Open Sound Control (OSC) - Advanced

This method provides a more direct, but manual, way to send and receive data. It's useful for connecting to software like TouchOSC, Pure Data, Max/MSP, or custom Python scripts.

### Core Concepts

OSC communication relies on three things being correctly configured on both ends:
1.  **IP Address:** The network address of the device you're sending data to.
2.  **Port Number:** The specific "channel" on that device to send data to.
3.  **OSC Address:** A text path that identifies the message (e.g., `/ch1/note`, `/mixer/fader1`).

### Patchworld OSC Setup

#### 1. Initial Configuration (using the [Execute](/blocks/system/execute) block)
The OSC connection must be configured within your patch.
1.  Spawn an [Execute](/blocks/system/execute) block.
2.  To set the destination IP address, type `remote_ip [IP_ADDRESS]` (e.g., `remote_ip 192.168.1.10`).
3.  To set the incoming port, type `port_in [PORT_NUMBER]` (e.g., `port_in 3330`).
4.  To set the outgoing port, type `port_out [PORT_NUMBER]` (e.g., `port_out 5550`).
5.  Trigger these [Execute](/blocks/system/execute) blocks once with a [Button](/blocks/interfaces/button) or `onload` event to set the configuration for the session. The `OSC Bridge` device in the library does this for you.

#### 2. Sending & Receiving Data

| Block | Thumbnail | Description |
|---|---|---|
| [OSC Send](/blocks/connectors/msg_out) | ![OSC Send thumbnail](https://portal.patchxr.io/block-thumbnails/msg_out.png =60x60) | Sends an OSC message. Set the OSC address in the text field (e.g. `/ch1cc1 :0`). The jolt input sends the trigger and its value is available as `:0`. |
| [OSC Receive](/blocks/connectors/msg_in) | ![OSC Receive thumbnail](https://portal.patchxr.io/block-thumbnails/msg_in.png =60x60) | Receives an OSC message matching the configured address (e.g. `/note1`) and emits a jolt with the received value. |

### Example Use Case: Community OSC/MIDI Bridge
The community has developed solutions using a Python script and TouchOSC to create a powerful OSC-to-MIDI bridge.

*   **Software:** A Python script (found on the [PatchXR GitHub](https://github.com/PatchXR/pyOscBridge-)) acts as the intermediary. It listens for OSC messages from Patchworld and converts them to MIDI for your DAW, and vice-versa.
*   **TouchOSC:** A mobile app that can be used as a flexible control surface, sending OSC messages directly to Patchworld over Wi-Fi. The community has created templates that map to specific OSC addresses.
*   **Typical Message Format:** The community has established a convention for OSC addresses to handle MIDI data:
    *   `/ch1note`: Note number for channel 1
    *   `/ch1vel`: Velocity for channel 1
    *   `/ch1noteoff`: Note off message
    *   `/ch1cc1`: CC message for controller #1 on channel 1
    *   `/ch1pitch`: Pitch bend for channel 1

---

## Wireless Jolt (Internal Wireless)

For routing jolts wirelessly **within** your patch — without any external software — use the wireless jolt blocks:

| Block | Thumbnail | Description |
|---|---|---|
| [Send Jolt](/blocks/connectors/wireless_out_jolt) | ![Send Jolt thumbnail](https://portal.patchxr.io/block-thumbnails/wireless_out_jolt.png =60x60) | Broadcasts a jolt to all Receive Jolt blocks sharing the same channel name. |
| [Receive Jolt](/blocks/connectors/wireless_in_jolt) | ![Receive Jolt thumbnail](https://portal.patchxr.io/block-thumbnails/wireless_in_jolt.png =60x60) | Receives a jolt from the matching Send Jolt block. |

These are ideal for connecting blocks across different groups or devices without drawing cables, and support multiplayer synchronization via the "Broadcast Multiplayer" inspector option on [Send Jolt](/blocks/connectors/wireless_out_jolt).

---

## Troubleshooting & Common Issues

*   **Connection Fails:** Ensure your headset and computer are on the **same Wi-Fi network**. Disable any firewalls on your computer that might be blocking the connection. In the Ableton OSC Bridge, you may need to click "Scan" multiple times.
*   **Order of Operations:** For the MIDI Companion App, **always start Patchworld on the headset first**, then launch the companion app on your computer.
*   **Latency:** There is inherent latency, especially sending signals *from* an external source *to* Patchworld. Sending signals *out* of Patchworld is generally faster. The headset's internal audio has latency; consider adjusting the **Buffer Size** in Patchworld's settings for a trade-off between performance and latency.
*   **Note Hanging / Retriggering:** When sending MIDI notes out of Patchworld, you must handle `note off` events. A common community solution is to send a jolt with a velocity of `0` to signify `note off`. Inside a receiving patch, you can use an [If Else](/blocks/logic/if_else) block to filter out these `0` value jolts so they don't retrigger a sound.
*   **Can't Find IP Address:** On your headset, go to `Wi-Fi Settings`, click on your connected network, and scroll down to find the IP address. On Windows, open Command Prompt and type `ipconfig`. On Mac, check `System Settings > Network`.