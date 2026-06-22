---
title: "Curve Editor"
date: 2025-10-01
draft: false
summary: "A Curve Editor implementing key interpolation via Bezier curves, Catmull-Rom splines, Hermite splines, and rotational interpolation via quaternion Catmull-Rom splines."
tags: ["technical", "C++", "real-time"]
type: ["technical", "post"]
---
***Since this was coursework, I can't make the project code public. Please reach out privately if interested!***


# About
For **Computer Animation Mathematics**, I implemented key interpolation via cubic Bezier curves, cubic Catmull-Rom splines, Hermite splines, and rotational interpolation via quaternion Catmull-Rom splines.
{{<youtubeLite id="mOK9xQzQFPw" label="Demo">}}

# Features
### Catmull-Rom Splines
I implemented various methods of computing Catmull-Rom splines for key points (1st-order continuous), including:
* **Bernstein Polynomials**
* **DeCasteljau's Algorithm**
* **Matrix Method**
### Hermite Splines
I implemented computing Hermite splines (2nd-order continuous) using matrices.
### Rotational Interpolation
I implemented rotational interpolation through Euler angle and quaternion interpolation, using spherical linear interpolation (slerp) with DeCasteljau's algorithm to create cubic quaternion Catmull-Rom splines.
