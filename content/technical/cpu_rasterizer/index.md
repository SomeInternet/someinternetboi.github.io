---
title: "CPU Rasterizer"
date: 2025-09-26
draft: false
summary: "A C++ CPU Rasterizer with Lambertian reflections, wireframe rendering, and FSAA."
tags: ["technical", "C++", "real-time"]
type: ["technical", "post"]
---
***Since this was coursework, I can't make the project code public. Please reach out privately if interested!***


# About
For [**Introduction to Computer Graphics**](https://www.cis.upenn.edu/~cis4600/current/index.html), I implemented a CPU rasterizer with lambertian reflections, wireframe rendering, and FSAA.


# Features
### Basic Rasterization Features
* **Coordinate Transformations** The rasterizer follows the world coordinates -> camera coordinates -> normalized device coordinates -> pixel coordinates sequence of transformations.
* **Triangle Rasterization**
* **Perspective-Correct Attribute Interpolation** Using the formula for perspective-correct attribute interpolation, I interpolated vertex attributes such as UV coordinates and normals, allowing for objects to be textured and shaded using techniques like Lambertian reflections.
### Additional Features
* **Lambertian Reflections** Using Lambert's Law of Cosines with interpolated fragment normals, I implemented Lambertian reflections with the camera as the light source.
* **Wireframe Rendering** By changing the triangle testing to only fill the edges, the rasterizer will render wireframes instead of full faces.
* **2x Full Scene Anti-Aliasing (FSAA)**