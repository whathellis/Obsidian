---
date: 2024-08-02
cssclasses:
  - daily
  - page-gray
  - Sunday
topics:
  - "[[Raytracing|Raytracing]]"
  - "[[Blender|Blender]]"
dg-publish: true
---
[[../../07/YouTube/Watched/Soft/Will Eevee 2.0 Replace Cycles - Blender 4.2|Will Eevee 2.0 Replace Cycles - Blender 4.2]]
#### Scene
##### Sampling
- Viewport
	- Samples: 12
	- [X] Temporal Reprojection
	- [X] Jittered Shadows
- Render
	- Samples: 64
- [X] Shadows
	- Rays: 4
	- Steps: 12
	- [ ] Volume Shadows
		- Steps: 16
	- Resolution: 1.000
- Advanced
	- Light Threshold: 0.010
##### Clamping
- Surface
	- Direct Light: 0
	- Indirect Light: 10
- Volume
	- Direct Light: 0
	- Indirect Light: 10
##### Raytracing
- Method: Screen-Trace
- Resolution: 1:1
- Max Roughness: 0.000
- Screen Tracing
	- Precision: 1.000
	- Thickness: 0.2 m
- [ ] Denoising
- Fast GI Approximation
	- Method: Global Illumination
	- Resolution: 1:1
	- Rays: 12
	- Steps: 64
	- Precision: 1.000 
	- Distance: 0 m
	- Thickness Near: 0.25 m
	- Far: 45°
	- Bias: 0.05
##### Volumes
##### Performance
##### Curves
##### Simplify
##### Depth of Field
##### Motion Blur
##### Film
#### World 
#####  Settings
- Light Probe
- Sun
	- Threshold: 
	- Angle:
	- [X] Shadow
#### Light
- Shadow
	- [X] Jitter: 10%
	- Filter: 1.00
	- Resolution Limit: 0.001 m
- Influence
	- Diffuse
	- Glossy
	- Transmission
	- Volume Scatter
#### Texture
##### Setting
- Surface




