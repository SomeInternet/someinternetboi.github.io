---
title: "OpenGL Monte Carlo Pathtracer"
date: 2026-03-14
draft: false
summary: "An OpenGL GLSL Monte Carlo Pathtracer featuring diffuse and specular reflective and transmissive materials, compound BSDFs (e.g. glass), multiple importance sampling (MIS), and depth of field via thin lens approximation."
tags: ["technical", "C++", "PBR", "OpenGL", "GLSL", "Global Illumination"]
type: ["technical", "post"]
---
***Since this was coursework, I can't make the project code public. Please reach out privately if interested!***


# About
For **Advanced Rendering**, I implemented an OpenGL GLSL Monte Carlo Pathtracer featuring diffuse and specular reflective and transmissive materials, compound BSDFs (e.g. glass), multiple importance sampling (MIS), and depth of field via thin lens approximation.

{{<youtubeLite id="xflTfC2P8eY" label="Demo">}}
# Features
### Basic Pathtracer Features
* **Monte Carlo Estimation**
* **Light Transport Equation**
* **Diffuse Material**
* **Specular Material** 
* **Compound BSDF (Glass, w/ Fresnel's Law)**
### Additional Features
* **Thin Lens Approximation** Using a thin lens approximation, where light enters the camera not through an infinitely small pinhole but through a lens, the pathtracer more accurately emulates the depth of field effect seen in real cameras.
* **Multiple Importance Sampling (MIS)** At each intersection, we cast 3 rays: 2 attempt to sample direct light from chosen light source (multiplying by the number of lights in the scene), of which 1 samples a point on the light and checks visibility, while the other samples according to the BSDF of the material, and checks if it hits the chosen light. The third ray samples indirect light, and is chosen according to the BSDF of the material. This leads to faster convergence times when compared to naively sampling.