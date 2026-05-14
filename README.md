# CineLink

OSC-controlled CineCamera for Unreal Engine, with optional in-engine fly-cam controller.

## Status
v0.1.0 — Blueprint-only proof of concept. C++ port planned.
⚠️ OSC functionality is under active development. Schema and behavior may change.

## Requirements
- UE 5.x
- OSC plugin (built-in, enable in project)

## Features

### OSC Receiver (in development)
Drive a CineCamera at runtime from any OSC source (TouchDesigner, browser apps, Python, etc.).

### FlyCam
Free-fly camera controller for use during Play mode, similar to the editor viewport camera. Useful for solo testing and LED volume work.

**Controls:**
- WASD — move
- Mouse — look
- Q / E — down / up
- Mouse Wheel — forward / backward
- Shift — speed boost
- R — reset to initial position

## Quick Start

### OSC
1. Copy to `Plugins/`, enable plugin
2. Drop `BP_CineLinkReceiver` in level
3. Drop `BP_CineLinkCamera` in level, assign to receiver's `TargetCamera`
4. Send OSC to port 8000

### FlyCam
1. Drop `BP_FlyCam` in level
2. Set Auto Possess Player: Player 0 (default)
3. Play

## OSC Schema (work in progress)

`/cinelink/cam/transform   f f f f f f   (tx ty tz rx ry rz, meters/degrees)`  
`/cinelink/cam/lens/focal  f             (mm)`  
`/cinelink/cam/lens/focus  f             (meters)`

## Roadmap
- v0.2: C++ port, multi-cam, bidirectional state, mode switching (FlyCam / External / Blend)