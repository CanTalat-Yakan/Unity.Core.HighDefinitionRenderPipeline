# Unity Essentials

This module is part of the Unity Essentials ecosystem and follows the same lightweight, editor-first approach.
Unity Essentials is a lightweight, modular set of editor utilities and helpers that streamline Unity development. It focuses on clean, dependency-free tools that work well together.

All utilities are under the `UnityEssentials` namespace.

```csharp
using UnityEssentials;
```

## Installation

Install the Unity Essentials entry package via Unity's Package Manager, then install modules from the Tools menu.

- Add the entry package (via Git URL)
    - Window → Package Manager
    - "+" → "Add package from git URL…"
    - Paste: `https://github.com/CanTalat-Yakan/UnityEssentials.git`

- Install or update Unity Essentials packages
    - Tools → Install & Update UnityEssentials
    - Install all or select individual modules; run again anytime to update

---

# HDRP Resources

> Quick overview: A ready‑to‑use set of HDRP assets - HDRP Asset, HDRP Global Settings, default LookDev profile, a default settings Volume Profile, and a global Volume Profile - to bootstrap projects quickly.

This package ships a minimal, sensible set of High Definition Render Pipeline (HDRP) assets under `Resources/` so you can get up and running fast. Assign the HDRP Asset and Global Settings in Project Settings, use the provided default Volume Profile as a baseline, and optionally drop a Global Volume into your scene using the included global profile. A LookDev profile is included for consistent lighting when using the Look Dev window.

![screenshot](Documentation/Screenshot.png)

## Features
- Preconfigured HDRP assets (in `Resources/`)
  - `HDRP Asset.asset` – the render pipeline asset to assign in Project Settings → Graphics
  - `HDRP Global Settings.asset` – pipeline global settings (default references and frame settings)
  - `Unity HDRP Default Settings Volume Profile.asset` – baseline post‑processing/lighting overrides for default use
  - `_UnityEssentials Global Volume Profile.asset` – a global volume profile you can apply to a scene‑level Global Volume
  - `Unity HDRP Default LookDev Profile.asset` – neutral LookDev profile for the Look Dev window
- Fast project bootstrap
  - Assign assets in Project Settings and have a working HDRP baseline within minutes
- Safe starting point
  - Use as‑is or duplicate and tweak to match your project’s needs
- Asset‑only module
  - No scripts; integrates with Unity’s HDRP configuration UI

## Requirements
- Unity Editor 6000.0+
- High Definition RP (HDRP) package installed (via Package Manager)
- Permissions to edit Project Settings (Graphics and HDRP)

Tip: Treat these as templates - duplicate and customize them rather than editing the originals if you want to preserve defaults.

## Usage
1) Assign the HDRP Asset
- Project Settings → Graphics → Scriptable Render Pipeline Settings → choose `HDRP Asset.asset`

2) Assign HDRP Global Settings
- Project Settings → HDRP → Use custom (if needed) → choose `HDRP Global Settings.asset`
- Inside Global Settings, ensure default references (e.g., Default Volume Profile) point to your preferred profile, such as `Unity HDRP Default Settings Volume Profile.asset`

3) Add a Global Volume to your scene (optional but recommended)
- GameObject → Volume → Global Volume (or add a Volume component and enable Global)
- Assign `_UnityEssentials Global Volume Profile.asset` as the Volume’s Profile to get a baseline of overrides

4) Use the Look Dev profile (optional)
- Window → Rendering → Look Dev → assign `Unity HDRP Default LookDev Profile.asset` for consistent lighting when evaluating materials/looks

5) Advanced: Make project‑specific copies
- Duplicate any of the assets into your own folder structure and reference your copies in Project Settings or scene Volumes

## How It Works
- These are standard HDRP assets saved under `Resources/` purely for convenience and discoverability
- Unity reads the HDRP Asset and Global Settings from Project Settings; the default Volume Profile reference inside Global Settings is used by the pipeline
- Scene‑level Global Volumes use the assigned Volume Profile at runtime; you can layer multiple Volumes as needed
- The Look Dev profile configures environment lighting for the Look Dev window

## Notes and Limitations
- Existing setups: If your project already uses HDRP, applying these assets may override prior settings; back up or duplicate first
- Version differences: HDRP settings/UI can vary between Unity versions; after assignment, verify quality, camera, and volume behavior
- Resources location: Assets are placed under `Resources/` for easy access, but they are standard assets and do not need to be loaded via code
- Addressables: Not used here; these assets are intended for Project Settings and scene references
- Source control: Assigning new HDRP assets modifies ProjectSettings; remember to add changes to VCS

## Files in This Package
- `Resources/HDRP Asset.asset`
- `Resources/HDRP Global Settings.asset`
- `Resources/Unity HDRP Default LookDev Profile.asset`
- `Resources/Unity HDRP Default Settings Volume Profile.asset`
- `Resources/_UnityEssentials Global Volume Profile.asset`
- `package.json` – Package manifest metadata

## Tags
unity, hdrp, resources, render pipeline, global settings, volume, volume profile, lookdev, graphics
