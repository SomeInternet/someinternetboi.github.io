---
title: "Mini-Minecraft"
date: 2025-12-08
draft: false
summary: "Minecraft clone made in C++, OpenGL, GLSL"
tags: ["technical", "C++", "OpenGL", "GLSL", "Minecraft", "real-time"]
type: ["technical", "post"]
---
***Since this was coursework, I can't make the project code public. Please reach out privately if interested!***

# About
For the final project in [**Introduction to Computer Graphics**](https://www.cis.upenn.edu/~cis4600/current/index.html), I worked in a group of 3 on a Mini-Minecraft clone in C++, OpenGL, and GLSL.

{{<youtubeLite id="6gKod2r6G8g" label="My contributions">}}

# Features
### Biome-Based Terrain Generation
I blended between **5 unique biomes** using 2 noise functions for temperature and humidity. The biomes included:
* Rolling grasslands
* Pillary highlands
* Deserts
* Snowcapped mountains
* Floating islands

I used boundary checks at the intervals to smoothly blend between different biomes, ensuring visually cohesive terrain.

The pillary highlands (inspired by [Zhangjiajie National Forest Park](https://en.wikipedia.org/wiki/Zhangjiajie_National_Forest_Park)) were made using Perlin, Worley, and Voronoi noise. The Worley noise was used to create mounds on the ground. the Perlin was used with smoothstep to place pillars, and the Voronoi cells were used to decide the heights of the pillars.

The deserts featured circular sand waves created using sined Worley noise.

The floating islands were created using 2 layers of noise: 1 to decide whether to place an island and another to determine its height. To prevent the islands from melting into the surrounding terrain, I took advantage of the cross-biome height blend, and only generated islands where the terrain height was 0.

### Noise-Based Cave Generation
I used 2 layers of 3D noise to create a mix of thinner, stringy caves and larger chasms. I then used a third layer of 3D noise to mix cobblestone and ores into the ground. I used static noise to place bedrock at the bottom of the world (excepting the floating islands biome) and to perturb the caverns, creating spiky ceilings. I also used the temperature and humidity values to create pools of water and lava bordered by deepslate.

### Shadow Mapping
I implemented shadow mapping, creating a depth buffer and running the terrain through a depth pass with an orthographic camera, before shading the terrain in the lambertian fragment shadow by sampling from the shadow map.

### Post-Processing Effects
I implemented a post-process crosshair which inverts the color of the background similar to real Minecraft. I also implemented a Kurosawa-inspired toggleable post-process shader which desaturates more muted colors while letting the vibrant colors pop, as well as creates outlines using Sobel edge detection. I also implemented underwater and underlava post processing effects.

### Procedural Sky
I implemented a raytraced procedural sky, using 2 layers of 3D Worley noise to emulate layers of clouds on an overcast day.

### Procedurally placed Assets
I scattered rocky mounds of mossy cobblestone across the grasslands, as well as procedurally generated trees in the grasslands and highlands biomes, with varying heights and leaf and log choices.

### Void, Cave, Distance Fog
I implemented distance fog, along with a vertical fog that changed color depending on temperature and humidity, allowing it to double as both a void fog and a cave fog. The strength of the vertical fog was calculated by dividing the fragment position by minimum of the player's height and a set other height, allowing it to always conceal the void but never overwhelm the player's vision.

### Swaying Leaves
Using time-based sine and cosine in conjunction with vertex locations, I changed the positions of the vertices of leaf blocks, creating a swaying effect.

### Grass Coloration
I used temperature and humidity to blend between 3 different grass colors, multiplying it by the value of the grassy portion of the texture to create biome-dependent grass colors that blended smoothly.