---
title: Console Commands
description: Updated via Unity Editor script
published: true
date: 2026-01-04T20:22:24.266Z
tags: 
editor: markdown
dateCreated: 2025-11-25T16:36:10.758Z
---

# Console Commands
_Generated on 1/4/2026 9:22:20 PM_

## How to use Console Commands
Console commands can be executed in PatchXR using the **Console Block**, **Execute Block**, or **Cmd Block**.

### Syntax
Commands are generally written as:
`CommandName <parameter1> <parameter2>`

Parameters are separated by spaces.
- **Float/Int**: Just write the number (e.g. `1.5`, `120`)
- **String**: If the string contains spaces, wrap it in quotes (e.g. `"My World Name"`)
- **Bool**: Use `true` or `false` (or `1`/`0`)

### Examples
**Setting the Tempo:**
```
SetTempo 128
```

**Changing Background Color (HSV):**
```
BgColorHSV 0.5 1 0.2
```

**Making a floater message**
```
ToasterMessage "Hello, world!"
```


## Quick Reference by Category

### Audio & Tempo
[`AbletonLinkEnabled`](#abletonlinkenabled) · [`AbletonLinkLatency`](#abletonlinklatency) · [`SetAudioEngineProcessingEnabled`](#setaudioengineprocessingenabled) · [`SetBufferSize`](#setbuffersize) · [`SetEngineBlockSize`](#setengineblocksize) · [`SetGhostRecordingGain`](#setghostrecordinggain) · [`SetMetronomeEnabled`](#setmetronomeenabled) · [`SetRecordVoice`](#setrecordvoice) · [`SetTempo`](#settempo)

### Visuals & Environment
[`AmbientColorHSV`](#ambientcolorhsv) · [`AmbientColorRGB`](#ambientcolorrgb) · [`BGColor1`](#bgcolor1) · [`BGColor2`](#bgcolor2) · [`BgColorHSV`](#bgcolorhsv) · [`FadeToBlack`](#fadetoblack) · [`FogColorHSV`](#fogcolorhsv) · [`FogColorRGB`](#fogcolorrgb) · [`FogFalloffMode`](#fogfalloffmode) · [`PlaceReflectionProbe`](#placereflectionprobe) · [`SetAntiAliasing`](#setantialiasing) · [`SetColorPalette`](#setcolorpalette) · [`SetMainLight`](#setmainlight) · [`SetPixelLightCount`](#setpixellightcount) · [`SetPostProcessing`](#setpostprocessing) · [`SetShadowDistance`](#setshadowdistance) · [`SetShadowQuality`](#setshadowquality)

### Player & Movement
[`AllowPlayerScaling`](#allowplayerscaling) · [`AllowPlayerTilt`](#allowplayertilt) · [`AllowSwimming`](#allowswimming) · [`SetGlobalSnapTurn`](#setglobalsnapturn) · [`SetGlobalSwimScaling`](#setglobalswimscaling) · [`SetGlobalTeleport`](#setglobalteleport) · [`SetGlobalUpsideDown`](#setglobalupsidedown) · [`SetPlayerHeadPosition`](#setplayerheadposition) · [`SetPlayerLimit`](#setplayerlimit) · [`SetPlayerPosition`](#setplayerposition) · [`SetPlayerScale`](#setplayerscale) · [`SetPlayerScaleMultiplier`](#setplayerscalemultiplier) · [`SetWorldSnapTurn`](#setworldsnapturn) · [`SetWorldSwimScaling`](#setworldswimscaling) · [`SetWorldTeleport`](#setworldteleport) · [`SetWorldUpsideDown`](#setworldupsidedown) · [`SwimToGazeAngle`](#swimtogazeangle) · [`SwimToGazeWeight`](#swimtogazeweight)

### Multiplayer
[`MPLobby`](#mplobby) · [`MPPopulatedWorld`](#mppopulatedworld) · [`MPRandom`](#mprandom) · [`MPSession`](#mpsession) · [`MPWorld`](#mpworld) · [`MPWorldLast`](#mpworldlast) · [`SetPause`](#setpause) · [`SetRegion`](#setregion) · [`TestMP`](#testmp)

### Editing & Patch Settings
[`AllowControlPanel`](#allowcontrolpanel) · [`AllowEditing`](#allowediting) · [`AllowForking`](#allowforking) · [`AllowJoltPatching`](#allowjoltpatching) · [`AllowOpenBubbles`](#allowopenbubbles) · [`AllowRadialMenu`](#allowradialmenu) · [`Autosaving`](#autosaving) · [`DisplayButtonText`](#displaybuttontext) · [`DisplayWirePlayMode`](#displaywireplaymode) · [`EditModeNumbers`](#editmodenumbers) · [`HideAll`](#hideall) · [`LockPatch`](#lockpatch) · [`PlayModeNumbers`](#playmodenumbers) · [`RemoveControlPanel`](#removecontrolpanel) · [`SetGridEnabled`](#setgridenabled) · [`SetRadialMenuProfile`](#setradialmenuprofile) · [`ShowAllHidden`](#showallhidden) · [`ShowHidden`](#showhidden) · [`ShowTooltips`](#showtooltips)

### Gen AI
[`GenerateAudio`](#generateaudio) · [`GenerateImage`](#generateimage) · [`GenerateModel`](#generatemodel) · [`GenerateSkybox`](#generateskybox) · [`GetSkyboxStyles`](#getskyboxstyles)

### Timeline
[`TimelineLength`](#timelinelength) · [`TimelineLoop`](#timelineloop) · [`TimelinePlay`](#timelineplay) · [`TimelineStop`](#timelinestop)

### Mixed Reality
[`PlaceAllWindows`](#placeallwindows) · [`SetMixedRealityMode`](#setmixedrealitymode) · [`SetSceneBounciness`](#setscenebounciness) · [`SetSyncPhysicalSpace`](#setsyncphysicalspace)

### World Loading & Navigation
[`AddRelatedWorld`](#addrelatedworld) · [`LoadFromCloud`](#loadfromcloud) · [`NextScene`](#nextscene) · [`OpenURL`](#openurl) · [`PreloadWorld`](#preloadworld) · [`PreviousScene`](#previousscene) · [`Script`](#script)

### Controllers & UI
[`HighlightControllerButton`](#highlightcontrollerbutton) · [`SetControllersVisible`](#setcontrollersvisible) · [`ShowHub`](#showhub) · [`ToasterMessage`](#toastermessage)

### Ghosts
[`DisableGhostHitInteractions`](#disableghosthitinteractions) · [`DisableGhostInteractions`](#disableghostinteractions) · [`RGR`](#rgr)

### Other
[`AllowControllerTipHide`](#allowcontrollertiphide) · [`AssignAccessLevel`](#assignaccesslevel) · [`CallEvent`](#callevent) · [`ChangeFogColor`](#changefogcolor) · [`ChangeFogDistance`](#changefogdistance) · [`CheckChangeRate`](#checkchangerate) · [`CurrentStateToTemp`](#currentstatetotemp) · [`EnableBeta`](#enablebeta) · [`GenerateModelFromImage`](#generatemodelfromimage) · [`GetCpuUsage`](#getcpuusage) · [`Go`](#go) · [`GoToTemp`](#gototemp) · [`LoadRPMAvatar`](#loadrpmavatar) · [`MakeCircle`](#makecircle) · [`OptoutAnalytics`](#optoutanalytics) · [`PhysicsClearOverride`](#physicsclearoverride) · [`PhysicsFreeze`](#physicsfreeze) · [`PhysicsReset`](#physicsreset) · [`PhysicsSavePositions`](#physicssavepositions) · [`PhysicsUnfreeze`](#physicsunfreeze) · [`QuestBoostThreshold`](#questboostthreshold) · [`QuestUnBoostThreshold`](#questunboostthreshold) · [`Save`](#save) · [`SelectAll`](#selectall) · [`SendAnalyticsEvent`](#sendanalyticsevent) · [`SetGameMode`](#setgamemode) · [`SetMarbleLifeTime`](#setmarblelifetime) · [`SetMarbleMaxCount`](#setmarblemaxcount) · [`SetMarbleMaxDistance`](#setmarblemaxdistance) · [`SetPowerBlockVisible`](#setpowerblockvisible) · [`SetTime`](#settime) · [`SetTimeScale`](#settimescale) · [`SetWorldResolutionMultiplier`](#setworldresolutionmultiplier) · [`ShowBlockList`](#showblocklist) · [`SpawnAsync`](#spawnasync) · [`Test123`](#test123) · [`TestInvite`](#testinvite) · [`TestRequest`](#testrequest)

---

## Full Reference

### AbletonLinkEnabled
**Parameters:** `bool value`
**Category:** Audio & Tempo

Console command to enable or disable ableton link.

---

### AbletonLinkLatency
**Parameters:** `Double value`
**Category:** Audio & Tempo

Console command to set the ableton link latency compensation.

---

### AddRelatedWorld
**Parameters:** `string pid`
**Category:** World Loading & Navigation

Command to specify which worlds are related to the current one. Related worlds will show up earlier in suggestions.

---

### AllowControllerTipHide
**Parameters:** `bool left, bool right`
**Category:** Other


---

### AllowControlPanel
**Parameters:** `bool enable`
**Category:** Editing & Patch Settings

De/activate the ability to open the control panel / Library. We keep the name as control panel for compatibility.

---

### AllowEditing
**Parameters:** `bool enable`
**Category:** Editing & Patch Settings

Set false to do not allow use edit mode

---

### AllowForking
**Parameters:** `bool enable`
**Category:** Editing & Patch Settings

Set false to do not allow users to save downloaded world

---

### AllowJoltPatching
**Parameters:** `bool isAllowed`
**Category:** Editing & Patch Settings

Enable Jolt wiring in playmode on visible blocks

---

### AllowOpenBubbles
**Parameters:** `bool enable`
**Category:** Editing & Patch Settings

De/activate the ability to open bubbles in the current patch.

---

### AllowPlayerScaling
**Parameters:** `bool enable`
**Category:** Player & Movement


---

### AllowPlayerTilt
**Parameters:** `bool enable`
**Category:** Player & Movement


---

### AllowRadialMenu
**Parameters:** `bool enable`
**Category:** Editing & Patch Settings

De/activate the ability to open the radial menu.

---

### AllowSwimming
**Parameters:** `bool enable`
**Category:** Player & Movement

De/activate swimming in current patch.

---

### AmbientColorHSV
**Parameters:** `float H, float S, float V`
**Category:** Visuals & Environment


---

### AmbientColorRGB
**Parameters:** `float r, float g, float b`
**Category:** Visuals & Environment


---

### AssignAccessLevel
**Parameters:** `int level`
**Category:** Other


---

### Autosaving
**Parameters:** `bool enable`
**Category:** Editing & Patch Settings

Enable/disable the autosaving feature

---

### BGColor1
**Parameters:** `float hue, float sat, float value`
**Category:** Visuals & Environment


---

### BGColor2
**Parameters:** `float hue, float sat, float value`
**Category:** Visuals & Environment


---

### BgColorHSV
**Parameters:** `float H, float S, float V`
**Category:** Visuals & Environment


---

### CallEvent
**Parameters:** `int handle, float value`
**Category:** Other


---

### ChangeFogColor
**Parameters:** `color col`
**Category:** Other


---

### ChangeFogDistance
**Parameters:** `float distance`
**Category:** Other


---

### CheckChangeRate
**Parameters:** `float newValue`
**Category:** Other


---

### CurrentStateToTemp
**Category:** Other


---

### DisableGhostHitInteractions
**Parameters:** `bool val`
**Category:** Ghosts


---

### DisableGhostInteractions
**Parameters:** `bool val`
**Category:** Ghosts


---

### DisplayButtonText
**Parameters:** `bool val`
**Category:** Editing & Patch Settings

Should touching button display more details about the button functionality.

---

### DisplayWirePlayMode
**Parameters:** `bool enable`
**Category:** Editing & Patch Settings

Should we display wires in Play mode (default true)

---

### EditModeNumbers
**Parameters:** `bool val`
**Category:** Editing & Patch Settings

Should we display numbers in Edit Mode.

---

### EnableBeta
**Parameters:** `bool enable`
**Category:** Other

Switch beta mode

---

### FadeToBlack
**Parameters:** `float time`
**Category:** Visuals & Environment


---

### FogColorHSV
**Parameters:** `float H, float S, float V`
**Category:** Visuals & Environment


---

### FogColorRGB
**Parameters:** `float r, float g, float b`
**Category:** Visuals & Environment


---

### FogFalloffMode
**Parameters:** `int mode`
**Category:** Visuals & Environment

Change how the fog varies according to the distance.

---

### GenerateAudio
**Parameters:** `int seconds, int steps, string prompt`
**Category:** Gen AI


---

### GenerateImage
**Parameters:** `string prompt`
**Category:** Gen AI


---

### GenerateModel
**Parameters:** `string prompt`
**Category:** Gen AI


---

### GenerateModelFromImage
**Parameters:** ` sv, MuXSelection& selection, MuXConsole& console`
**Category:** Other


---

### GenerateSkybox
**Parameters:** `string prompt`
**Category:** Gen AI


---

### GetCpuUsage
**Category:** Other


---

### GetSkyboxStyles
**Category:** Gen AI


---

### Go
**Parameters:** `string command`
**Category:** Other


---

### GoToTemp
**Category:** Other


---

### HideAll
**Category:** Editing & Patch Settings

This method changes Visibility parameter for every block at scene.

---

### HighlightControllerButton
**Parameters:** `string controller, string button, float glow, float freq`
**Category:** Controllers & UI

Highlight a button on one of the controllers. Syntax: highlightcontrollerbutton [left|right] [button] [strength] [frequency] e.g. highlightcontrollerbutton left hub 0.8 2 available buttons are: pistoltrigger grip thumbstick button1 button2 hub Use strength zero to turn off the highlight.

---

### LoadFromCloud
**Parameters:** `string productId`
**Category:** World Loading & Navigation

Load world from the cloud used by magic portals in Landing patch

---

### LoadRPMAvatar
**Parameters:** `string url`
**Category:** Other


---

### LockPatch
**Parameters:** `bool isAllowed`
**Category:** Editing & Patch Settings

Make all blocks locked or unlocked

---

### MakeCircle
**Parameters:** `string blockName, int count, float r`
**Category:** Other

Spawn a bunch of object arranged in a circle around 0, 0, 0

---

### MPLobby
**Parameters:** `string productId`
**Category:** Multiplayer

Show list of rooms for specific world

---

### MPPopulatedWorld
**Parameters:** `string productId, string sessionNameModifier, Action`1 customJoin`
**Category:** Multiplayer

Join most populated session in multiplayer

---

### MPRandom
**Category:** Multiplayer

Join to random session

---

### MPSession
**Parameters:** `string productId`
**Category:** Multiplayer

Join to session with unique name

---

### MPWorld
**Parameters:** `string productId`
**Category:** Multiplayer

Join to most oldest room that has space

---

### MPWorldLast
**Parameters:** `string productId`
**Category:** Multiplayer

Join to latest room

---

### NextScene
**Parameters:** `string filePath`
**Category:** World Loading & Navigation


---

### OpenURL
**Parameters:** `string url`
**Category:** World Loading & Navigation


---

### OptoutAnalytics
**Parameters:** `bool enable`
**Category:** Other

Disable analytics across all sessions

---

### PhysicsClearOverride
**Category:** Other

Clears any manual physics freeze override and returns to automatic game mode logic. In multiplayer, broadcasts to all players.

---

### PhysicsFreeze
**Category:** Other

Freezes physics simulation, making all physics objects kinematic. Overrides the automatic game mode logic until PhysicsUnfreeze or PhysicsClearOverride is called. In multiplayer, broadcasts to all players.

---

### PhysicsReset
**Category:** Other

Resets all physics objects to their edit mode positions and zeroes velocities. Useful for resetting physics simulations without toggling play/edit mode. In multiplayer, broadcasts to all players.

---

### PhysicsSavePositions
**Category:** Other

Saves current positions of all physics objects as their new starting positions. Useful for updating the reset point after objects have settled or been repositioned. In multiplayer, broadcasts to all players.

---

### PhysicsUnfreeze
**Category:** Other

Unfreezes physics simulation, allowing physics objects to move again. Overrides the automatic game mode logic until PhysicsFreeze or PhysicsClearOverride is called. In multiplayer, broadcasts to all players.

---

### PlaceAllWindows
**Category:** Mixed Reality


---

### PlaceReflectionProbe
**Category:** Visuals & Environment


---

### PlayModeNumbers
**Parameters:** `bool val`
**Category:** Editing & Patch Settings

Should we display numbers in Play Mode.

---

### PreloadWorld
**Parameters:** `string world`
**Category:** World Loading & Navigation

Preload worlds from the cloud at patch was started

---

### PreviousScene
**Parameters:** `string filePath`
**Category:** World Loading & Navigation


---

### QuestBoostThreshold
**Parameters:** `float value`
**Category:** Other


---

### QuestUnBoostThreshold
**Parameters:** `float value`
**Category:** Other


---

### RemoveControlPanel
**Category:** Editing & Patch Settings

Command to remove control panel from current scene Requires for intro world, mask editor and other scenes with limited interaction

---

### RGR
**Category:** Ghosts

Temporary remove restrictions for ghosts in current world

---

### Save
**Category:** Other


---

### Script
**Parameters:** `string filename`
**Category:** World Loading & Navigation

Load script in json format

---

### SelectAll
**Category:** Other


---

### SendAnalyticsEvent
**Parameters:** `string message`
**Category:** Other

Send analytics message to cloud. Message will be put with a name executeEvent and parameter name EventName (Gad set these names on cloud side)

---

### SetAntiAliasing
**Parameters:** `int v`
**Category:** Visuals & Environment


---

### SetAudioEngineProcessingEnabled
**Parameters:** `bool value`
**Category:** Audio & Tempo


---

### SetBufferSize
**Parameters:** `int bufferSize`
**Category:** Audio & Tempo


---

### SetColorPalette
**Parameters:** `string colorList`
**Category:** Visuals & Environment


---

### SetControllersVisible
**Parameters:** `bool enable`
**Category:** Controllers & UI

This method makes controllers for current user in/visible.

---

### SetEngineBlockSize
**Parameters:** `int blockSize`
**Category:** Audio & Tempo

Change the size of buffer blocks inside audio engine

---

### SetGameMode
**Parameters:** `string mode`
**Category:** Other


---

### SetGhostRecordingGain
**Parameters:** `float gain`
**Category:** Audio & Tempo

Sets the recording gain in db.

---

### SetGlobalSnapTurn
**Parameters:** `bool enable`
**Category:** Player & Movement

Enable or disable snap turn in player preference settings.

---

### SetGlobalSwimScaling
**Parameters:** `bool enable`
**Category:** Player & Movement

Enable or disable Swim Scaling in player preference settings.

---

### SetGlobalTeleport
**Parameters:** `int mode`
**Category:** Player & Movement

-1: do nothing 0: no joystick up movement 1: teleport 2: jetpack

---

### SetGlobalUpsideDown
**Parameters:** `bool enable`
**Category:** Player & Movement

Enable or disable swim upside down in player preference settings.

---

### SetGridEnabled
**Parameters:** `bool enable`
**Category:** Editing & Patch Settings

Enables or disables snapping to the grid when blocks are moved.

---

### SetMainLight
**Parameters:** `float x, float y, float z, float r, float g, float b`
**Category:** Visuals & Environment


---

### SetMarbleLifeTime
**Parameters:** `float lifetime_seconds`
**Category:** Other


---

### SetMarbleMaxCount
**Parameters:** `int maxMarbleCount`
**Category:** Other


---

### SetMarbleMaxDistance
**Parameters:** `float distance`
**Category:** Other


---

### SetMetronomeEnabled
**Parameters:** `bool value`
**Category:** Audio & Tempo

Console command for enabling or disabling the metronome.

---

### SetMixedRealityMode
**Parameters:** `string mode`
**Category:** Mixed Reality

Sets the mixed reality mode to used. See the MixedRealityMode enum for available options.

---

### SetPause
**Parameters:** `bool pause`
**Category:** Multiplayer


---

### SetPixelLightCount
**Parameters:** `int v`
**Category:** Visuals & Environment


---

### SetPlayerHeadPosition
**Parameters:** `float x, float y, float z, float rx, float ry, float rz, float rw`
**Category:** Player & Movement


---

### SetPlayerLimit
**Parameters:** `float minX, float maxX, float minY, float maxY, float minZ, float maxZ`
**Category:** Player & Movement

Stops player movement when reaching the boundaries. Boundaries in meters. SetPlayerLimit 0 0 0 0 0 0 will result in no boundaries at all. Display as red wired box in the editor scene view.

---

### SetPlayerPosition
**Parameters:** `float x, float y, float z`
**Category:** Player & Movement


---

### SetPlayerScale
**Parameters:** `float newScale`
**Category:** Player & Movement


---

### SetPlayerScaleMultiplier
**Parameters:** `float newScale`
**Category:** Player & Movement


---

### SetPostProcessing
**Parameters:** `int v`
**Category:** Visuals & Environment


---

### SetPowerBlockVisible
**Parameters:** `bool val`
**Category:** Other


---

### SetRadialMenuProfile
**Parameters:** `int profile`
**Category:** Editing & Patch Settings


---

### SetRecordVoice
**Parameters:** `bool enable`
**Category:** Audio & Tempo

Set a value controlling if ghost voice recording should be enabled.

---

### SetRegion
**Parameters:** `string region`
**Category:** Multiplayer

Force switching home multiplayer region for the player

---

### SetSceneBounciness
**Parameters:** `float floorCeilingBounciness, float wallsWindowsDoorsBounciness, float desksOthersBounciness`
**Category:** Mixed Reality

Sets the bounciness of the different kinds of objects in the mixed reality scene.

---

### SetShadowDistance
**Parameters:** `float v`
**Category:** Visuals & Environment


---

### SetShadowQuality
**Parameters:** `int v`
**Category:** Visuals & Environment


---

### SetSyncPhysicalSpace
**Parameters:** `bool val`
**Category:** Mixed Reality


---

### SetTempo
**Parameters:** `Double x`
**Category:** Audio & Tempo


---

### SetTime
**Parameters:** `Double x`
**Category:** Other


---

### SetTimeScale
**Parameters:** `float val`
**Category:** Other


---

### SetWorldResolutionMultiplier
**Parameters:** `float multiplier`
**Category:** Other


---

### SetWorldSnapTurn
**Parameters:** `bool enable`
**Category:** Player & Movement

Force snap turn feature for current world

---

### SetWorldSwimScaling
**Parameters:** `bool enable`
**Category:** Player & Movement

Force Swim Scaling feature for current world

---

### SetWorldTeleport
**Parameters:** `int mode`
**Category:** Player & Movement

-1: not forcing 0: forcing no joystick up movement 1: teleport 2: jetpack

---

### SetWorldUpsideDown
**Parameters:** `bool enable`
**Category:** Player & Movement

Force swim upside down feature for current world

---

### ShowAllHidden
**Parameters:** `bool show`
**Category:** Editing & Patch Settings


---

### ShowBlockList
**Category:** Other


---

### ShowHidden
**Parameters:** `bool show`
**Category:** Editing & Patch Settings


---

### ShowHub
**Parameters:** `bool toBeOpened`
**Category:** Controllers & UI

Open hub from the console

---

### ShowTooltips
**Parameters:** `bool visibility`
**Category:** Editing & Patch Settings

Show or hide tooltips in current patch.

---

### SpawnAsync
**Parameters:** `string sv`
**Category:** Other


---

### SwimToGazeAngle
**Parameters:** `float val`
**Category:** Player & Movement


---

### SwimToGazeWeight
**Parameters:** `float val`
**Category:** Player & Movement


---

### Test123
**Category:** Other


---

### TestInvite
**Category:** Other


---

### TestMP
**Category:** Multiplayer

Console commands to create and join to mp sessions

---

### TestRequest
**Category:** Other


---

### TimelineLength
**Parameters:** `float value`
**Category:** Timeline

Console command to stop timeline playback.

---

### TimelineLoop
**Parameters:** `bool value`
**Category:** Timeline

Console command to stop timeline playback.

---

### TimelinePlay
**Category:** Timeline

Console command to start timeline playback.

---

### TimelineStop
**Category:** Timeline

Console command to stop timeline playback.

---

### ToasterMessage
**Parameters:** `string s`
**Category:** Controllers & UI


---

