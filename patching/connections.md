---
title: Connections
description: 
published: true
date: 2025-12-10T06:36:12.395Z
tags: 
editor: markdown
dateCreated: 2025-08-13T16:14:29.543Z
---

# Stream
Stream connections are used to pass audio and other continuous signals.
Data flows at the speed of systems sample rate.

Usage example:
Spawn an oscillator block, multiplier and an output (speaker).
Connect the oscillator output fork using the trigger button, pull it out and connect into the multiplayer input. Set the multiplier on a low value like 0.1
Connect the multiplier output to the output block.
You should hear the tone produced by the oscillator.

# Jolt
Jolts pass single event based data. For example a button pressed might output the event via a jolt output. 
They have purple connections. 

Notice you can convert Stream to Jolt using a "Stoe" block. This will trigger the jolt on each sample.

# Tag
aka Sticks aka Reff connections are to make reference connections between blocks. They are used with blocks that have a stick connector. [insert image of stick connector]