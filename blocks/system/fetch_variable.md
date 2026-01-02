# fetch_variable

**Category**: ⚙️ System

![fetch_variable thumbnail](https://portal.patchxr.io/block-thumbnails/fetch_variable.png)

## Description

Fetch a value (text or number) from the server, can collect value from your other worlds. (usage: display the best score, save player progress in worlds)

Tip: you can add prefix to restrict to a player, getting the player's name or ID using the "Players" & "Get Name" block, and use it to name your var "PlayerID/HasVisitedMyWorld" = 1. So you can know if a player visited your world from any other world.

## Inputs, Outputs and Parts

**Key**: Name your variable here, will identify your value on the server.

**Text Output**: Connect a "Text" block here to visualize the result.

**Fetch**: Attempt to fetch the value post online.

**Fetched Value**: If the Key is found on the server, this will output its value.

**On Fail**: If the value does not exist, this will be trigger with a value of 0.

---

*Last updated: 2026-01-02 05:47*