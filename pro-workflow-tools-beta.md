---
layout: default
title: Pro Workflow Tools
permalink: /pro-workflow-tools-beta/
robots: noindex, nofollow
---

<img class="splash" src="{{ '/assets/pro-workflow-tools/splash.png' | relative_url }}" alt="ProWorkflowTools">

<h2 class="beta-heading">Downloads</h2>
<p class="download-label">Latest</p>
<ul class="downloads">
  <li><a href="{{ '/releases/ProWorkflowTools_0.1.1_UE5.7_Win64.zip' | relative_url }}">ProWorkflowTools 0.1.1 — UE 5.7 Win64</a></li>
  <li><a href="{{ '/releases/ProWorkflowTools_0.1.1_UE5.8_Win64.zip' | relative_url }}">ProWorkflowTools 0.1.1 — UE 5.8 Win64</a></li>
</ul>
<p class="download-label">Older</p>
<ul class="downloads downloads-older">
  <li><a href="{{ '/releases/ProWorkflowTools_0.1.0_UE5.7_Win64.zip' | relative_url }}">ProWorkflowTools 0.1.0 — UE 5.7 Win64</a></li>
  <li><a href="{{ '/releases/ProWorkflowTools_0.1.0_UE5.8_Win64.zip' | relative_url }}">ProWorkflowTools 0.1.0 — UE 5.8 Win64</a></li>
</ul>

<h2 class="beta-heading">Install</h2>
<ol class="install">
  <li>Unzip it and move the <code>ProWorkflowTools</code> folder into <code>YourProject/Plugins/</code>.</li>
  <li>Launch the project.</li>
  <li>Enable <strong>Pro Workflow Tools</strong> under <strong>Edit → Plugins</strong>, then restart.</li>
</ol>

<h2 class="beta-heading readme-heading">Readme</h2>

<div class="post-body" markdown="1">

# Unreal Engine: Pro Workflow Tools

Level editor tools for environment artists and world builders based on my AAA game dev experience working with many other professional DCC apps and custom game engines.

If you came to Unreal from Maya, Blender or Max, you know the sluggish and clunky feeling on Unreal Engine level editing: drag-selecting, scaling, duplicating, etc. all are lacking features present in most DCCs. Pro Workflow Tools overhauls many aspects of level editor workflows, selections, groups, gizmo, manipulating material assignments, and a ton more! All designed around hotkey-focused workflow.

Enable the plugin, then configure it under **Editor Preferences → Plugins → Pro Workflow Tools**. Every feature has its own on/off switch there; all are on by default.

| Engine | Status |
| --- | --- |
| 5.6 | Supported |
| 5.7 | Supported |
| 5.8 | Supported |
| Older than 5.6 | Not supported |

---

### What's included

- **DCC Standard Control Scheme**: LMB marquee select, Shift add, Ctrl subtract, Ctrl+LMB deselect, Select Similar marquee
- **Interactive Decal Placement**: live preview, drag to size, collections, modifier hotkeys
- **Actor Grid Paint**: click-drag to tile the selected static mesh or decal on its modular grid
- **Material Clipboard**: hold a key to pick, apply and clear material overrides
- **Super Groups**: enter and exit locked groups; Ctrl+G pivot and folder options
- **Bounding Box Scale**: `B` for face, edge and corner bounds scaling
- **Per-Actor Origin Scale / Rotate**: hold `Shift` on the Scale or Rotate widget to transform each actor about its own origin
- **Duplicate With Last Transform**: `Shift+D`
- **Duplicate In Place**: `Ctrl+D` with no grid offset
- **Allow Re-selecting Actors**: Shift+click an already selected actor to make it the pivot
- **Show Last Hidden**: `Ctrl+Alt+H` restores the last batch you hid with `H`

---

## Features

![Pro Workflow Tools]({{ '/assets/pro-workflow-tools/welcome.png' | relative_url }})

### Hotkeys

| Action | Default | Notes |
| --- | --- | --- |
| Duplicate with Last Transform | `Shift+D` | Replays the last transform. Works with multiple actors selected. |
| Bounding Box Scale | `B` | Cage scale while the Scale widget is active. Also a toggle button next to Scale in the viewport toolbar. |
| Show Last Hidden | `Ctrl+Alt+H` | Unhides the last batch hidden from the selection, one step back rather than Show All |
| Interactive Decal Placement | `J` | Needs Interactive Decal Placement enabled |
| Actor Grid Paint | `T` | Needs Actor Grid Paint enabled (takes over `T` while it is) |
| Material Clipboard | hold `Tab` | Needs Material Clipboard enabled; the key is set in its settings |
| Enter / Exit Group | `Enter` / `Shift+Enter` | Needs Super Groups enabled |

Rebind under **Editor Preferences → Keyboard Shortcuts** (search "Pro Workflow Tools").

### Bounding Box Scale

<img class="demo" src="{{ '/media/pro-workflow-tools/Vid_BoxScale_01.webp' | relative_url }}" alt="Bounding Box Scale">
<img class="demo" src="{{ '/media/pro-workflow-tools/Vid_BoxScale_02.webp' | relative_url }}" alt="Bounding Box Scale">
<img class="demo" src="{{ '/media/pro-workflow-tools/Vid_BoxScale_Grid.webp' | relative_url }}" alt="Bounding Box Scale with grid snap">

Press `B` (or the box button after Scale in the viewport toolbar), then use the Scale widget (`R`). Face, edge and corner handles scale the bounds. The opposite side stays put and the actor pivot moves with it.

- **Alt** while dragging: both sides move and the bounds center stays put. Alt+click on a handle starts that drag; Alt+click elsewhere still orbits
- **V** while dragging: snap the handle to a vertex on another mesh. A face stays on its axis, an edge on its two axes, a corner goes to the vertex
- **Ctrl** while dragging: uniform scale along the handle's line from the opposite side (or from the center with Alt). Can be toggled mid-drag
- **Shift**: precision. Grid snap (faces) and scale snap (edges, corners, uniform factor) follow the toolbar
- Flat axes (default 5% of the longest side) hide their face handles. Edge and corner drags leave that axis alone unless Ctrl is held
- Tool HUD: Faces / Edges / Corners checkboxes (saved per user)
- Targets one placed primitive actor or one selected component. Level Instances and Blueprint actors are not caged as a whole; select one of their components (static mesh, ISM, HISM) instead
- Preferences: flat ratio, cage color, edge/corner color, handle size

### Per-Actor Origin Scale / Rotate

<img class="demo" src="{{ '/media/pro-workflow-tools/Vid_PerActorTransform.webp' | relative_url }}" alt="Per-Actor Origin Scale and Rotate">

With several actors selected and the Scale (`R`) or Rotate (`E`) widget up, hold `Shift` (configurable) while dragging. Each actor scales or rotates about its own origin instead of the shared pivot.

- Origin markers show each actor's pivot while the modifier is held, in the hovered axis colors (all three for the uniform scale handle or free-rotate ball)
- Translate is not affected; Alt+drag duplicate still works
- Stands down while another tool (Box Scale, Grid Paint, Decal Placement) has replaced the gizmo

### DCC Standard Control Scheme

- **LMB drag**: replace the selection with the marquee contents
- **Shift + LMB drag**: add to the selection
- **Ctrl + LMB drag**: subtract from the selection
- **Ctrl + Shift + LMB drag**: select similar (mesh or class)
- **Ctrl + LMB click** on a selected actor: deselect it

In perspective viewports an LMB drag marquees instead of moving the camera. Alt orbit/dolly/track, RMB look and WASD flight work as before.

### Duplicate In Place

`Ctrl+D` / Edit → Duplicate puts the copy exactly on the original (no grid nudge). Alt+drag duplicate is not affected.

### Allow Re-selecting Actors

**Shift + LMB click** on an already selected actor makes it the last selected: the transform pivot moves to it and `Ctrl+G` uses it as the group pivot. Independent of the DCC control scheme.

### Material Clipboard

<img class="demo" src="{{ '/media/pro-workflow-tools/Vid_MaterialClipboard_01.webp' | relative_url }}" alt="Material Clipboard">

Hold `Tab` (configurable). The cursor becomes an eyedropper; then:

- **MMB**: pick the material under the cursor
- **LMB**: apply (double-click applies to all slots)
- **RMB**: clear the override (double-click clears all slots)

Only Material and Material Instance assets can be picked. Slots are matched by name across the selection. Instanced meshes and foliage can't be picked from or applied to.

### Actor Grid Paint

<img class="demo" src="{{ '/media/pro-workflow-tools/Vid_GridPaint_01.webp' | relative_url }}" alt="Actor Grid Paint">

Select exactly one static mesh or decal actor and press `T`:

- The source actor defines the grid: its pivot and rotation, and either mesh bounds × scale or, for decals, the YZ size on the receiving plane
- A ghost follows the cursor over a soft cell overlay. **Prevent Intersect** on the tool HUD stops copies from being painted into other actors (saved per user)
- **LMB drag** paint · **Shift+LMB** erase this session's tiles · **Ctrl+LMB** line fill · **B** edit bounds
- Painted cells pop and erased cells shrink out as short outline pulses; there is no text by the cursor during a stroke
- Occupied, blocked and erase-hover cells stay flat on the grid plane as a tinted footprint (erase adds faint corner brackets for the actor's extent) so the art underneath stays visible
- The grid fades out in a world-space circle, so long pieces don't stretch it into an oval
- **Ctrl** line fill: an anchor dot and axis guides from the last painted cell, the run previewed in the hover-cell style, and a live `+N` count by the cursor
- For meshes the paint plane follows the camera (a short "Plane XY" label appears when it switches); decals paint on the receiving plane
- Edit bounds (`B`): a live size readout while dragging a face, then "Bounds applied" on commit
- Thin axes are never stacked. Cells already painted this session are skipped; intersection prevention is optional
- Esc or `T` exits. The transform gizmo is hidden while the tool is active

### Super Groups

<img class="demo" src="{{ '/media/pro-workflow-tools/Vid_SuperGroup_01.webp' | relative_url }}" alt="Super Groups">

- **Enter** a locked group to edit inside it; **Shift+Enter** exits
- **Double-click** a group member to enter its group; inside a group, double-click a nested group's member to step into that one (setting: Double-Click To Enter Groups)
- While inside a group, a viewport bar shows **Exit Group** plus the **Visualize Editing** and **Restrict Selection** toggles (saved to settings)
- `Ctrl+G` can use the **last selected actor as pivot** and can nest the new group in an Outliner folder
- Actors added while editing join the active group
- Group pivot icons: Show → Advanced → Group Pivot Icons

### Interactive Decal Placement

<img class="demo" src="{{ '/media/pro-workflow-tools/Vid_Decal_01.webp' | relative_url }}" alt="Interactive Decal Placement">
<img class="demo" src="{{ '/media/pro-workflow-tools/Vid_Decal_Edit_01.webp' | relative_url }}" alt="Editing a placed decal">

Press `J`:

- Live preview, corner-anchored or centered (HUD **Centered** toggle; tap **Alt** to switch, or hold Alt during a drag to invert it for that drag). Click to stamp, drag to size
- Camera controls are untouched: Alt+LMB orbits, Alt+MMB pans, RMB flies with WASD and wheel speed. The tool's keys and scroll bindings step aside while RMB is held
- **MMB** on a scene decal edits it in place; **MMB** on empty space goes back to placing. **Shift+MMB** copies that decal's material, size, flips, opacity and sort into the next placement
- Pressing `J` with one decal selected edits that decal. **Inherit Selected Decal On Enter** (on by default) also copies its settings onto the next placement. Leaving the tool clears the selection
- Category and Decal in the HUD are dropdowns
- The preview lands on the surface drawn under the cursor. Static meshes, instances and foliage use their render triangles, so missing or simplified collision doesn't matter. Translucent surfaces follow the editor's **Allow Translucent Selection**. Landscape, BSP and other primitives use their own collision
- **Shift+Scroll** size · **Ctrl+Scroll** rotate · **W+Scroll** depth (dashed guide on the preview, outward from the image) · **T+Scroll** alpha · **S+Scroll** sort
- **Scroll** / **Tab+Scroll** change decal / category
- `R` random rotation and `Backspace` reset apply to the next stamp, not while editing a placed decal. `X` / `Z` flip horizontal / vertical · `C` Fit Surface · Space move · Shift (while dragging) uniform
- **Fit Surface** (HUD checkbox, `C`, off by default): the preview tilts to the average of the surface under its footprint (center, corners, edge midpoints) while hovering and dragging, so it sits flat on curved or uneven geometry. The dragged corner stays under the cursor and the sampled points are drawn while dragging. Projection depth is left to you
- Size, Depth, Angle, Alpha and Sort in the HUD are click-to-edit: type a value (`256 x 128`, `45`, `75%`), Enter applies it, Esc cancels. The next drag or scroll overrides it as usual
- Every hotkey and scroll change shows a short fading readout by the cursor ("Flip V on", "Depth 128 cm", "Opacity 75%")
- Ctrl chords (Ctrl+Z, Ctrl+S, ...) always reach the editor; the single-key hotkeys never take them
- Sources come from the Content Browser or from **Collections** (a per-user list; the project's list is copied into it once, on first run). The welcome splash can create an example decal material and collection for you
- Placed decals can be nested under `Decals/<category>` folders and join the active Super Group when you are editing one

---

## Requirements

- Unreal Engine 5.6, 5.7 or 5.8
- Editor-only C++ source plugin: the project must be able to compile C++

## Installation

1. Copy this folder to `YourProject/Plugins/ProWorkflowTools/` (or `Engine/Plugins/Editor/ProWorkflowTools/` in an engine source build).
2. Generate project files and build, or let the editor compile it on first launch.
3. Enable **Pro Workflow Tools** in **Edit → Plugins** (it is off by default) and restart.

## Settings

**Editor Preferences → Plugins → Pro Workflow Tools**

| Section | Options |
| --- | --- |
| **Viewport Controls** | DCC Standard Control Scheme; Allow Re-selecting Actors; Select Similar Marquee Notification |
| **Viewport Overlays** | Tools Accent Color (shared by Decal Placement, Grid Paint and Material Clipboard) |
| **Bounding Box Scale** | Enable; Flat Axis Ratio (default `0.05`); cage color; edge/corner handle color; handle size (default `12` px) |
| **Per-Actor Origin Transform** | Enable; modifier key (default `Shift`); Show Origin Markers |
| **Duplicate** | Duplicate In Place |
| **Material Clipboard** | Enable; hold key (default `Tab`) |
| **Actor Grid Paint** | Enable; Intersect Test Bounds Scale (default `0.85`); Thin Axis Threshold (default `12.5` cm) and Relative Ratio (default `0.12`) |
| **Super Groups** | Enable; Use Last Selected Actor As Group Pivot; Nest New Groups In Outliner Folder; Visualize Group Editing; Restrict Selection While Editing; Double-Click To Enter Groups; pivot icon options |
| **Decal Placement** | Enable; Inherit Selected Decal On Enter; Decal Collections; Default Projection Depth (`24` cm); Min Drag Extent (`5` cm); Preview Plane Extent (`128` cm); Rotation Scroll Interval (`5°`); Size Scroll Interval (`5` cm); Use Last Placed Size; Nest Placed Decals |

Project settings save to `Config/DefaultEditor.ini`. Per-user settings for this project (HUD checkboxes, the welcome splash "Don't show again", and your own Decal Collections list) save to `Saved/Config/<Platform>/EditorPerProjectUserSettings.ini`. The project's Decal Collections list is copied into the per-user list once, on first run.

## Building

Build the project's Editor target with the editor closed:

```bat
Engine\Build\BatchFiles\Build.bat YourProjectEditor Win64 Development -Project="Path\To\YourProject.uproject" -WaitMutex -NoXGE
```

Add `-Module=ProWorkflowTools` to compile only this plugin. Live Coding (Ctrl+Alt+F11) works for source edits that don't touch `Build.cs`.

Building and testing against several engine versions, and the release process, are described in [Docs/ENGINE_SUPPORT_AND_REVIEW.md](https://github.com/modsoft/ue-editor-extensions/blob/main/Docs/ENGINE_SUPPORT_AND_REVIEW.md).

## Copyright

Copyright © 2026 Trey McNair. All rights reserved.

</div>
