---
title: Live Sessions
description: 
published: true
date: 2025-08-15T19:32:22.399Z
tags: 
editor: markdown
dateCreated: 2025-08-14T19:12:20.361Z
---

# Live Sessions (Multiplayer)

Live Sessions allow multiple users to join the same world simultaneously to jam, collaborate on creations, or share experiences. This guide covers the basics of creating, joining, and managing multiplayer sessions in PatchWorld.

## The Multiplayer Watch
When you are in a multiplayer session, a "multiplayer watch" interface will be available on your controller. This menu is your primary tool for session moderation, allowing you to see who is in the room and manage their permissions.

## Finding and Joining a Session

You can find active Live Sessions in two main ways:

### From the Hub
1.  Open the main menu in the Hub.
2.  Above the menu, a **Room List** will appear, showing all currently available public sessions.
3.  Simply click on a session to join it.

### Using the Room List Block
For custom worlds or hubs, you can spawn a `room_list` block. This block will display the same list of active public sessions, allowing you to create custom portals or social areas.

> **Note on Assets:** When you join a world, any custom assets like 3D models (.glb), sounds (.wav, .ogg), or images will be downloaded automatically. Depending on the size of the world and your internet connection, this may take a moment.

## Creating a Session

By default, any Live Session you start is **Public**, meaning anyone can see it in the Room List and join.

### How to Start a Session
You can start a Live Session from several places:
*   **From the World Info Page:** Navigate to one of your worlds in the Hub and select the option to start a Live Session.
*   **From Solo Mode:** Enter one of your worlds in "Play Solo" mode. Open the world widget menu to find the option to "Make Live Room".
*   **From the Menu:** If a world is set to multiplayer by default, opening it may directly initiate a live session.

### Joining vs. Creating a New Session
A key behavior to understand is that PatchWorld prioritizes joining existing sessions.

> **Important:** If you start a Live Session for a world that already has an active session running (e.g., "Jam Room"), you will **join the existing session** instead of creating a new, separate one.

To guarantee you are creating a fresh, empty session, it is best to first enter the world in **Play Solo** mode and then start the Live Session from the in-world menu.

## Session Types: Public vs. Private

*   **Public Sessions (Default):** Visible to everyone in the Hub's Room List.
*   **Private Sessions:** Do not appear in the public list. To join, a user must be invited or accept a request.

To make a running session private:
1.  As the host, open the Hub menu.
2.  Navigate to the World Info widget for your current session.
3.  Click the triple-dot menu (`...`).
4.  Select **"Make Session Private"**.

If a user tries to join a private session, the host will receive a request to approve or deny their entry.

## Moderation and Permissions

As the creator or host of a world, you have control over what other users can do.

*   **The Moderation Menu:** The multiplayer watch on your wrist shows a list of all players in the session. From here, you can manage individual permissions. Common permissions include:
    *   **Mic:** Mute or unmute a player for others.
    *   **Touch:** Allow or disallow a player from interacting with devices.
    *   **Edit:** Grant or revoke the ability for a player to enter edit mode and modify the world.
*   **World Permissions:** Some settings (like world visuals or physics) can only be changed by users with edit permissions. If you join a world where you don't have these rights, you can use the **"Save Copy"** option to create your own version of the world that you can fully edit.

## Current Limitations & Known Issues

Multiplayer is an evolving feature. Here are some known issues and limitations the community has encountered:

*   **Physics Sync:** Physics-based objects (like those using `make_physical`, `thruster`, or `joint` blocks) are not fully synchronized between players yet. One player may see an object move, while others do not. The developers are actively working on a fix.
*   **Limited Editing Tools:** When in a multiplayer session, some editing functions in the `Inspector` menu are disabled for performance and stability reasons, even for users with full permissions.
*   **Voice Chat Problems:** Occasionally, users may not be able to hear each other. Restarting the PatchWorld app usually resolves this. Also, ensure you have granted microphone permissions to the app in your headset's settings.
*   **Connection & Loading Issues:**
    *   A stable internet connection is crucial for a good multiplayer experience. A 5GHz Wi-Fi network is recommended over 2.4GHz.
    *   Sometimes, loading a world can appear to get "stuck" at 75%. Be patient, as it is often still downloading large assets in the background.
*   **Multiple Headsets on One Account:** Due to Meta's platform restrictions, you cannot have two headsets join the same multiplayer session if they are both logged into the same Meta account. Each player needs their own unique account.
*   **Version Mismatch:** All players in a session should be on the same version of PatchWorld (e.g., all on the live public version, or all on the same beta version) to avoid instability.

## Tips for Creators & Organizers

*   **Local vs. Shared Controller Data:** Blocks that read controller data (like `Controller_Rotation` or `Get_Controller_Position`) are **local to each player**. This means if you build a device controlled by hand movements, each player will see it react to their *own* hands, not the host's. This is important to consider when designing multiplayer experiences.
*   **Organizing a Session:** For workshops or planned jams, it's a good practice to have everyone meet in a Discord voice channel first. This helps coordinate everyone to join the PatchWorld room at the same time, which can prevent issues with players getting split into different instances.
*   **Performance is Key:** Be mindful of the number and complexity of assets (especially high-polygon models and long audio files) in your world. While it may run fine on a powerful PC, it can cause performance issues for players on standalone Quest headsets. Hiding complex block arrangements inside devices when not being edited can significantly improve performance for everyone.
