---
title: Video capturing 
description: 
published: true
date: 2025-08-27T21:40:09.659Z
tags: 
editor: markdown
dateCreated: 2025-08-27T10:12:41.438Z
---

# Recording Control Commands Reference

## 🎬 Basic Recording

| Command | Description |
|---------|-------------|
| `record` or `RecordToggle` | Toggle recording on/off |
| `RecordStart` | Start recording |
| `RecordStop` | Stop recording |
| `RecordScreenshot` | Take a screenshot |
| `RecordStatus` | Show current recording status |

## ⚙️ Recording Settings

| Command | Description |
|---------|-------------|
| `RecordMode [2D\|VR\|360]` | Set capture mode (default: 2D) |
| `RecordResolution [720/1080/1440/2160/2880/3450/4320]` | Set resolution
| `RecordFramerate [fps]` | Set framerate (default: 30) |
| `RecordQuality [Low\|Medium\|High\|Ultra]` | Set quality preset |
| `RecordCodec [H264\|HEVC]` | Set video codec |
| `RecordAudio [on\|off]` | Enable/disable audio recording |
| `RecordPostFX [on\|off]` | Enable/disable post-processing effects |
| `RecordSettings` | Show current settings |

## 📋 Presets

| Command | Description |
|---------|-------------|
| `RecordPreset [name]` | Apply preset (StreamLow, StreamHigh, Archive, Quick) |
| `RecordListPresets` | List available presets |

## 🎯 Spawning Commands

### Auto-Spawn Settings

| Command | Description |
|---------|-------------|
| `RecordAutoSpawn [on\|off]` | Auto-spawn recordings as blocks after capture |
| `RecordAutoSpawnStatus` | Check auto-spawn status |

### Spawn Position Control

| Command | Description |
|---------|-------------|
| `RecordSpawnPosition [front\|origin\|custom]` | Set spawn position mode |
| `RecordSpawnCoords [x] [y] [z]` | Set custom spawn coordinates |
| `RecordSpawnDistance [distance]` | Set distance from player (default: 0.5) |

**Spawn Position Options:**
- `front` - In front of player (default)
- `origin` - At world origin (0,0,0)
- `custom` - At custom coordinates

### Manual Spawning

| Command | Description |
|---------|-------------|
| `RecordSpawnLast` | Manually spawn the last recording |
| `RecordSpawn [path]` | Spawn specific video/image file |

## 🛠️ Utility Commands

| Command | Description |
|---------|-------------|
| `RecordHelp` | Show help for all commands |
| `RecordFolder` | Show recording output folder path |
| `RecordOpen` | Open recordings folder (desktop only) |
| `RecordList` | List recent recordings |

## 📁 Output Folders

### Android/Quest
- **Videos:** `/sdcard/Oculus/VideoShots/PatchXR/`
- **Screenshots:** `/sdcard/Oculus/Screenshots/PatchXR/`

### Desktop
- **Videos:** `Patch/Recordings/Videos/`
- **Screenshots:** `Patch/Recordings/Screenshots/`

## 💡 Example Usage

### Start HD recording with auto-spawn
```
RecordAutoSpawn on
RecordPreset StreamHigh
RecordStart
```

### Take screenshot and spawn it in front
```
RecordSpawnPosition front
RecordScreenshot
```

### Record 360 video at origin
```
RecordMode 360
RecordSpawnPosition origin
RecordToggle
```

> **Note:** All recordings automatically spawn as appropriate blocks (image/video/360video) when auto-spawn is enabled, positioned according to the spawn settings.