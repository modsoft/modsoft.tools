---
layout: post
title: Blender QuickCollision
permalink: /quickcollision-for-blender/
---

Quickly generate game engine compliant collision meshes.

<img width="1920" height="1080" alt="qc_splash" src="{{ '/assets/quickcollision/qc_splash.png' | relative_url }}" />

# Features

- Generate box, sphere, capsule, and convex colliders from any object or Edit Mode selection
- Automatic Unreal Engine standard naming convention (`UBX_`, `USP_`, `UCP_`, `UCX_`) and suffix numbering `_00`, `_01`,...
- Colliders can be auto-parented to their source, gathered into a dedicated collection, and displayed as wireframe.
- **Convex generation generated with an implementation of StanHull** — Stan Melax's approximating hull algorithm from the PhysX toolchain. (Credit to Stan Melax and John Ratcliff.)

<img width="1366" height="768" alt="previews_01" src="{{ '/assets/quickcollision/previews_01.png' | relative_url }}" />

<img width="1366" height="768" alt="previews_02" src="{{ '/assets/quickcollision/previews_02.png' | relative_url }}" />

- **Compact UI Mode** `Settings > Compact View`

<img width="318" height="233" alt="image" src="{{ '/assets/quickcollision/compact-ui.png' | relative_url }}" />

## Install

Blender 4.2 or newer.

Check Releases or Code > Download Zip for latest.

Drag the zip onto Blender, or install from **Edit → Preferences → Get Extensions → Install from Disk**.
The tools are in the **Quick Collision** tab of the 3D Viewport sidebar.

## License

The add-on (Python) is **GPL-3.0-or-later**. See [LICENSE](https://github.com/modsoft/blender-quickcollision/blob/main/LICENSE).

- **StanHull** (`native/`, `stanhull-win64.dll`, `stanhull-linux64.so`): BSD-3-Clause. See [native/LICENSE](https://github.com/modsoft/blender-quickcollision/blob/main/native/LICENSE) and [NOTICE](https://github.com/modsoft/blender-quickcollision/blob/main/NOTICE).
- **Icons** (`icons/*.png`): [CC0 1.0](https://github.com/modsoft/blender-quickcollision/blob/main/icons/LICENSE).
