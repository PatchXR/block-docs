# Post Var

**Category**: ⚙️ System

![post_variable thumbnail](https://portal.patchxr.io/block-thumbnails/post_variable.png)

## Description

Post a value (text or number) to the server, can be then collected by other worlds, or other player visiting this world. (usage: display the best score, save player progress in worlds)

Tip: you can add prefix to restrict to a player, getting the player's name or ID using the "Players" & "Get Name" block, and use it to name your var "PlayerID/HasVisitedMyWorld" = 1. So you can know if a player visited your world from any other world.

## Inputs, Outputs and Parts

**Value**: Value to push the server.

**Key**: Name your variable here, will identify your value on the server.

**Text inputs**: Text value to send, you can connect: "Text", "Get Name" or "Join & Apply Text" blocks.

**Post**: Will post the value to the server.

**On Done**: There can be a delay before the value is posted. Once done, this output will fire a 1.

---

*Last updated: 2026-01-02 06:30*