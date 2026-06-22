---
title: "Mesh Editor"
date: 2025-10-31
draft: false
summary: "A C++ OpenGL mini mesh-editor implementing the half-edge data structure representation of meshes, with Catmull-Clark subdivision."
tags: ["technical", "C++", "OpenGL", "GLSL", "real-time"]
type: ["technical", "post"]
---
***Since this was coursework, I can't make the project code public. Please reach out privately if interested!***

# About
For [**Introduction to Computer Graphics**](https://www.cis.upenn.edu/~cis4600/current/index.html), I worked on a light mesh editor that implemented the half-edge mesh data structure.
{{<youtubeLite id="zO7bD9FgBzg" label="Demo">}}

# Features
### Mesh Loading From OBJ Files
The program is able to parse and load in .obj files storing 3D meshes.

### Mesh Editing
The program is able to edit meshes via vertex movement, face coloring, and edge splitting.

### Catmull-Clark Subdivision
I implemented [Catmull-Clark subdivision](https://en.wikipedia.org/wiki/Catmull%E2%80%93Clark_subdivision_surface).