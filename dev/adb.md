---
title: adb
description: 
published: true
date: 2026-01-21T23:22:51.345Z
tags: 
editor: markdown
dateCreated: 2025-08-27T15:10:09.386Z
---


# Unity Android Logs - Quick Guide

## Get Unity Logs

### Option 1: Start Fresh 
```bash
adb logcat -c
adb logcat -s Unity > unity_log.txt
```
Clears old logs, then saves all Unity logs from now on. **Stop with Ctrl+C**.

### Option 2: Dump What's Available
you want more history when dumpin.
Set buffer to 128MB (default is usually 256KB). :
```bash
adb logcat -G 128M
```
dump:
```bash
adb logcat -d -s Unity > unity_log.txt
```
Gets recent Unity logs still in memory (usually last few minutes). Not reliable for older logs due to limited buffer.




---
**For bug reports:** Use Option 1, reproduce the bug, then stop logging.


# scrcpy
no crop: `scrcpy -m 1600 -b 25m`
left eye crop: `scrcpy --crop 2064:2208:0:0 -m 1600 -b 25m `
if needed add:
`--no-audio `

