---
title: "Physically-Based Deferred Renderer"
date: 2026-03-14
draft: false
summary: "A physically-based deferred renderer in OpenGL and GLSL, with diffuse and glossy convolution for environment map reflections on materials with roughness and metallic factors, and deferred rendering for screen space reflections"
tags: ["technical", "C++", "real-time", "PBR", "OpenGL", "GLSL"]
type: ["technical", "post"]
---
***Since this was coursework, I can't make the project code public. Please reach out privately if interested!***


# About
First, fragment properties were saved into the G-buffer. This included the albedo, the world space position, the normal, and PBR factors like metallic (red channel) and roughness (blue channel). The mask (green channel) simply denoted the presence or lack of geometry for screen space reflection calculations.
![GBuffer](images/gbuffer.png)

The physically based shading of the materials had to be computed prior to the screen space reflections. Diffuse and glossy convolution were used to compute the environment map reflections on the objects.
![PBR Shading](images/pbr.png)

The reflections were computed through screen space raymarching rather than world space raymarching for optimization with a limited number of iterations (that way, we didn't waste time searching the same pixel of the G-buffer). The effect on material roughness on the reflections was naively approximated by creating blurred versions of the reflection, then interpolating between them using the roughness value.
![Reflection Blurs](images/blurs.png)

The result is good-enough looking reflections that take into account varying material roughnesses.
![Screen Space Reflections](images/ssr.png)