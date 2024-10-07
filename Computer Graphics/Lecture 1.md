# Introductory

A definition of **Image**
- A combination of objects, lights and viewers (or camera).
- Represents visual information, stored in photographic films, canvas or digitally.
- Some methods to acquire digital image: Scanner, Digital camera, computer graphics.

A definition of **Digital Image**
- Raster-based, where a raster is an array of pictures elements — pixel.
- Collection of pixels produce image.
- *Resolution*: number of pixels in unit area, density of pixels.
- *Pixel per inch* (PPI) or Pixel per centimeter (PPCM): measurements of the resolution of an electronic image device like monitor.
- *Horizontal* and *vertical density* share the same thing.

**Image Processing** is the analysis and manipulation of a digitized image for enhancing quality.
- Improving the contrast -> easier for a human to interpret
- Noise-reduction filters -> for clearer image
- Automatic recognition of objects
- Determining a person's identity by examining an image of their fingerprint

**Image Synthesis** is an image generation referring to the construction of an image from scratch, rather processing an existing images.

Synthesis of a 2D image from a 3d scene description is known to be *rendering*.

## Computer Graphics

**Computer Graphics** (CG) the creation, storage and manipulation of models and images by a computer.

Components of Computer Graphics:
- Computer Hardware: Input, display/output and processing devices.
- Computer Software
	- Special-purpose programs - Adobe
	- General graphics libraries - OpenGL

Involvement:
- How pictures are represented in CG.
- How pictures are prepared for presentation.
- How interaction within the pictures is accomplished.

Main tasks:
- **Imaging**: representing 2D images
- **Modeling**: (shape) representing the geometry of objects in the 3D world
- **Rendering**: (light, perspective) generating 2D images of the objects
- **Animation**: (movement) describing how objects change in time

## Importance of CG

1. Display of Information
2. Design
3. Simulation and Animation

## Types of CG

- Batch Computer Graphics
	- Known as offline rendering, where you achieve the final result of the image
- Interactive Computer Graphics
	- Known as real-time computer graphics

## Graphics Library

- A built-in functions to draw
- Cross-platform
- Elements of a graphics library are:
	- Primitives
	- Attributes
	- Light sources
	- Transformations
	- Immediate mode and retained mode

*Immediate mode*: no stored representation, package holds only attribute state, and application must completely draw each frame.

*Retained mode*: library compiles and displays from scene graph that it maintains.

# Basic Components Of A Graphics System

- Pixel: Picture Element
- Resolution: Number of pixels per unit video display
- Display Size: Measured as distance from one corner to the diagonally opposite corner
- Viewing Angel: It is angel from which the screen can be seen from side
- Persistence: How long a phosphor continue to emit light.
	- Lower persistence phosphor needs higher refresh rate; to maintain picture without flicker
- Response Time: minimum time to change pixels color
- Brightness: The amount of light emitted from display
- Aspect Ratio: Ration of vertical points to horizontal points to produce equal-length lines in both directions on the screen

Six major elements in a computer graphics system:
1. Input devices
2. CPU
3. GPU
4. Memory
5. Frame buffer
6. Output devices

## Input Devices

- Relative-positioning device
	- Digitizers
	- Data Glove
- Logical input device
	- String device
	- Locator

## Output Devices

- Display systems are referred to as Video Monitor or Video Display Unit (VDU)