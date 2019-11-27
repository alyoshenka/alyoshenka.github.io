---
title: Anatomy of an Outline Shader
peek: a step-by-step explanation of an outline shader using depth and normals texture
---

I made an outline shader in Unity following a wonderful tuorial linked [here](https://roystan.net/articles/outline-shader.html "Link to original outline shader tutorial"). This is an explanation of how it works. 
> Please note, this code is very heavily influenced by the linked tutorial, and I give full credit to the author.

// gif

### Setup
The finished shader is supplied to a material, which is then supplied to a script (FulscreenPostprocessing.cs in my case) that also takes in the main scene camera as a parameter. This script sets the cameras depth texture mode such that the camera will write both depth and normals into its buffer. Just before the image is rendered to the screen, this script takes the camera's view, applies the given shader to it, and outputs it to the screen. The result is the normal camera view overlaid with outlines around objects.

// gif?

#### Shader Variables


_MainTex | The main texture to work with, gets camera view rendered in on graphics blit
--- | --- | ---
_Outline | outline color 
--- | --- | ---
_Scale | __add__
--- | --- | ---
_DepthThreshold | __add__
--- | --- | ---
_NormalThreshold | __add__
--- | --- | ---
_DepthNormalThreshold | __add__
--- | --- | ---
DepthNormalThresholdScale | __add__


#### Vertex Shader
Pretty standard vertex shader, the only additional things it does is calculate the view apace direction of the camera

// img?

#### Vertex -> Fragment data
Holds typical vertex and uv data, as well as a variable for the view space matrix of the camera

// img?


### Fragment Shader 
> How it all works

Outlines are formed around the edges of an object. The question of how to make an outline shader then becomes 'How can I detect the edges of an object?' In this case, edge detection is done by checking the difference in depth (measured from the camera) between two points, and the difference between the directions these two faces are pointing. 

// more explanation


#### Depth

Every frame, the main camera renders into a depth texture that can be accessed from inside the shader. To check the depth of the current point and compare it to those around it, we must first figure out what and where these "points around it" are going to be. In this case, I am picking four points diagonally from the starting point (in an x shape). Using these points, I can access the depth of each one by reading from the camera depth texture. 

// dpeth only image

