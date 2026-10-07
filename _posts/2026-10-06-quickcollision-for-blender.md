---
layout: post
title: Blender QuickCollision
permalink: /quickcollision-for-blender/
---

Hey! I'm sharing a free Blender add-on I've been working on for generating game-engine ready collision meshes.  
  
QuickCollision can generate various box, sphere, capsule, and convex collision meshes from your selection, with game-engine-compliant collision naming. Convex hull generation uses an implementation of the StanHull algorithm from the PhysX toolchain. Inspired by a similar tool I was missing when switching from Maya to Blender. Hope others find this useful!  
  
It’s free and open source here: <a href="https://github.com/modsoft/blender-quickcollision" target="_blank" rel="noopener">github.com/modsoft/blender-quickcollision</a>



Full details:

---

![qc_splash]({{ '/assets/quickcollision/qc_splash.png' | relative_url }})

# Features

- Generate box, sphere, capsule, and convex colliders from any object or Edit Mode selection
- Automatic Unreal Engine standard naming convention (`UBX_`, `USP_`, `UCP_`, `UCX_`) and suffix numbering `_00`, `_01`,...
- Colliders can be auto-parented to their source, gathered into a dedicated collection, and displayed as wireframe.
- **Convex generation generated with an implementation of StanHull** — Stan Melax's approximating hull algorithm from the PhysX toolchain. (Credit to Stan Melax and John Ratcliff.)

![previews_01]({{ '/assets/quickcollision/previews_01.png' | relative_url }})

![previews_02]({{ '/assets/quickcollision/previews_02.png' | relative_url }})

- **Compact UI Mode** `Settings > Compact View`

![image]({{ '/assets/quickcollision/compact-ui.png' | relative_url }})

## Install

Blender 4.2 or newer.

Check Releases or Code > Download Zip for latest.

Drag the zip onto Blender, or install from **Edit → Preferences → Get Extensions → Install from Disk**.
The tools are in the **Quick Collision** tab of the 3D Viewport sidebar.

## License

The add-on (Python) is **GPL-3.0-or-later**. See [LICENSE](https://github.com/modsoft/blender-quickcollision/blob/main/LICENSE).

- **StanHull** (`native/`, `stanhull-win64.dll`, `stanhull-linux64.so`): BSD-3-Clause. See [native/LICENSE](https://github.com/modsoft/blender-quickcollision/blob/main/native/LICENSE) and [NOTICE](https://github.com/modsoft/blender-quickcollision/blob/main/NOTICE).
- **Icons** (`icons/*.png`): [CC0 1.0](https://github.com/modsoft/blender-quickcollision/blob/main/icons/LICENSE).

