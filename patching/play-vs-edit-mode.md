---
title: Play VS Edit mode
description: 
published: true
date: 2025-08-15T19:35:19.557Z
tags: 
editor: markdown
dateCreated: 2025-08-15T19:35:17.321Z
---

### Understanding Play vs. Edit in Patchworld

One of the most fundamental concepts in Patchworld is the distinction between **Play Mode** and **Edit Mode**. These two states govern everything from how you interact with instruments to how physics behave. Understanding the difference is the key to unlocking your full creative potential and avoiding common frustrations.

Think of it like being on a theater stage. **Edit Mode** is when you are the stagehand: the house lights are on, you can see all the ropes and wiring, and your job is to move props, connect cables, and build the set. **Play Mode** is showtime: the stage lights come on, the backstage machinery disappears, and you become the performer, interacting with the set as the audience would.

---

#### The Core Difference at a Glance

| Feature | Play Mode (Performance) | Edit Mode (Workshop) |
| :--- | :--- | :--- |
| **Purpose** | Experiencing and performing in the world. | Building, wiring, and debugging the world. |
| **Controllers** | Your chosen avatar hands are visible. | Controllers appear as grey, functional tools. |
| **Visibility** | Hidden objects are **invisible**. You see the world as a visitor would. | Hidden objects are **visible** (often tinted green) so you can edit them. |
| **Interaction** | You can play instruments, grab designated handles, and use interactive devices. | You can select, move, delete, group, and inspect any object. |
| **Physics** | **Active.** Marbles fall, joints move, and thrusters propel. | **Disabled.** Physics objects are frozen in their saved positions for easy editing. |
| **Key Action** | You *play* the creation. | You *build* the creation. |

---

#### How to Switch Between Modes

The naming can be a little confusing at first. The primary way to switch the *entire world's state* is through the main Hub menu.

**The Main Method (Global Switch):**
1.  Open the main menu (Y/B button).
2.  Navigate to the **World** tab (the icon with the planet and characters).
3.  You will see two key buttons at the top:
    *   **"Hide Hidden"**: This activates **Play Mode**.
    *   **"Show Hidden"**: This activates **Edit Mode**.

**The Quick Method (Local Toggle):**
You can also use your **radial menu** (press the A/X button on an empty space) to temporarily toggle visibility. This is useful for quickly "peeking behind the curtain" to adjust something without fully leaving Play Mode. However, the global state set in the World menu is what determines the default behavior.

---

#### What You Can Do in Each Mode

##### In Edit Mode (The Workshop 🛠️)

This is your primary creation space. Here you can:
*   **Build & Wire:** Spawn blocks, devices, and assets from the library and connect them with stream (thick) and jolt (thin) cables.
*   **Organize:** Use the **grip button** to select multiple objects (resize the selection sphere with the joystick). You can then **Group** them, turn them into a reusable **Device**, or **Copy/Paste** them.
*   **Inspect:** The radial menu's **Inspect** option is your best friend. It opens a panel allowing you to lock an object's position, change its properties (like color or a constant value), and ungroup devices to see their inner workings.
*   **Arrange:** Use the **Ruler** block and the world's **Grid** (found in the World settings) to align objects with precision.
*   **See the Guts:** All the blocks you've chosen to "Hide in Play Mode" are visible here, allowing you to debug your wiring without visual clutter during performance.

##### In Play Mode (The Performance 🎭)

This mode is for experiencing the world you've built.
*   **Interact:** Play your instruments, pull levers, press buttons, and use any interactive elements you've designed. This is where devices like the `e-string` bow become functional.
*   **Activate Physics:** Marbles will start rolling, `make_physical` objects will respond to gravity, and your complex contraptions will spring to life.
*   **The Final Look:** You see your creation as your visitors will—clean, polished, and with all the backstage wiring hidden away.
*   **Perform:** Your ghost recordings will play back, sequencers will run, and your musical or interactive experience will unfold as intended.

---

#### Common Troubleshooting: "Why Isn't This Working?"

Understanding the two modes solves the most frequent issues new patchers face:

*   **"I'm hitting my instrument, but it's not making a sound!"**
    *   *You are likely in Edit Mode.* Switch to Play Mode ("Hide Hidden") to perform.

*   **"My marbles won't fall / My thruster isn't moving!"**
    *   *You are in Edit Mode, where physics are paused.* Switch to Play Mode to see them in action.

*   **"I can't select, move, or delete anything!"**
    *   *You are likely in Play Mode.* Switch to Edit Mode ("Show Hidden") to access your building tools.

*   **"My world is a mess of wires and green blocks!"**
    *   *You are in Edit Mode.* Switch to Play Mode to see the clean, finished version of your world.

Mastering the flow between these two modes is essential. Build in Edit, test in Play, and soon you'll be creating complex, interactive worlds with confidence. Happy patching