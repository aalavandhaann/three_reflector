# three_reflector

A simple utility to make a mesh reflect its sorroundings. This can be used in three.js as well as as an aframe component. This utility can be used with a color, or one texture image, or two texture images. USeful in a scenario to reflect the ground with the scene. This shader is an extension of threejs mirror example. 

### API

| Property   | Description | Default Value |
| ---------- | ----------- | ------------- |
| color | String – Color of the mesh without textures  | #848485
| intensity | Number – A value between 0.0 to 1.0 that controls the intensity of the reflection. 0 implies no reflection and 1.0 implies a mirror| 0.5 |
| textureWidth | Number – The width of texture created with scene reflection| 256 |
| textureHeight | Number – The height of texture created with scene reflection| 256 |
| wrapOne | Vector2 – The wrap repeat value for the first texture image. Ignored if no textures are used.| {x:1, y:1}} |
| wrapTwo | Vector2 – The wrap repeat value for second texture image. Ignored if no textures are used.| {x:1, y:1}} |
| invertedUV | Boolean – For models exported from Blender or tools with Z-Up, this is an ugly hack to invert the Y-coordinates of the UV map.| False |
