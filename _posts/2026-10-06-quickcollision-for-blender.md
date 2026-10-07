---
layout: post
title: QuickCollision for Blender
---

Collision meshes are the quiet part of a game asset. The visible mesh can be as detailed as it needs to be. The shape the engine tests against should be a box, a sphere, a capsule, or a convex hull, named the way Unreal already expects.

[QuickCollision](https://github.com/modsoft/blender-quickcollision) is a Blender add-on that builds those shapes from an object, or from a selection in Edit Mode. It applies the Unreal prefixes `UBX_`, `USP_`, `UCP_`, and `UCX_`, then numbers them `_00`, `_01`, and so on. Colliders can be parented back to the source, gathered into their own collection, and drawn as wireframe so they stay out of the way of the render mesh.

Convex hulls are generated with an implementation of StanHull, Stan Melax’s approximating hull from the PhysX toolchain. That part of the credit belongs to Stan Melax and John Ratcliff.

The tools sit in the 3D Viewport sidebar, on the Quick Collision tab. A compact layout is under Settings when the panel is taking more room than it should.

It requires Blender 4.2 or newer. The current release is 0.1.0. Download the zip from the repository, drag it onto Blender, or install it from **Edit → Preferences → Get Extensions → Install from Disk**.

The add-on is GPL-3.0-or-later. StanHull is BSD-3-Clause. The icons are CC0.

Source and installs live at [github.com/modsoft/blender-quickcollision](https://github.com/modsoft/blender-quickcollision).
