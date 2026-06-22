---
title: "Shader Viewer"
date: 2025-10-17
draft: false
summary: "A vertex and fragment shader viewer implementing various materials and post processing effects."
tags: ["technical", "C++", "OpenGL", "GLSL", "real-time"]
type: ["technical", "post"]
---
***Since this was coursework, I can't make the project code public. Please reach out privately if interested!***


# About
For [**Introduction to Computer Graphics**](https://www.cis.upenn.edu/~cis4600/current/index.html), I worked on a shader viewer implementing various materials and post processing effects.
{{<youtubeLite id="1JcJDUIo23g" label="Demo">}}

# Features
### Material Fragment Shaders
* **Blinn-Phong Reflections** Using the camera as a light source, I implemented the highlights of Blinn-Phong reflections on top of Lambertian reflections and ambient lighting.
* **Matcap Materials** Matcap materials map normals to locations in a 2D image that "bakes" a material, allowing for things like reflections to be quickly faked.
### Post-Process Fragment Shaders
Using a post processing pass, I implemented the following post-process effects:
* **Gaussian Blur** by sampling neighboring pixels multiplied by a weight corresponding to the blur radius and strength. I check for the edge of the frame to prevent darkening at the borders.
* **Sobel Filter (Edge Detection)** Sobel samples neighboring pixels with a kernel matrix to detect sudden changes in color.
* **Underwater Filter** By applying a blue tint and sampling pixels using perturbed noise varied by time, I emulated the effects warping effect of being underwater. I performed a second sample to create a ghosting effect, and also applied a vignette effect to darken the borders.