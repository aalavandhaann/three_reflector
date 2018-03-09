# three_reflector

A simple utility to make a mesh reflect its sorroundings. This can be used in three.js as well as as an aframe component. This utility can be used with a color, or one texture image, or two texture images. USeful in a scenario to reflect the ground with the scene. This shader is an extension of threejs mirror example. 

### API

| Property   | Description | Default Value |
| ---------- | ----------- | ------------- |
| color | String – Color of the mesh without textures  | #848485
| intensity | Number – A value between 0.0 to 1.0 that controls the intensity of the reflection. 0 implies no reflection and 1.0 implies a mirror| 0.5 |
| blendIntensity | Number – A value between 0.0 to 1.0 that controls the blendIntensity between the two textures if given| 0.5 |
| textureWidth | Number – The width of texture created with scene reflection| 256 |
| textureHeight | Number – The height of texture created with scene reflection| 256 |
| wrapOne | Vector2 – The wrap repeat value for the first texture image. Ignored if no textures are used.| {x:1, y:1}} |
| wrapTwo | Vector2 – The wrap repeat value for second texture image. Ignored if no textures are used.| {x:1, y:1}} |
| invertedUV | Boolean – For models exported from Blender or tools with Z-Up, this is an ugly hack to invert the Y-coordinates of the UV map.| False |

### Example
```
<!DOCTYPE html>
<html>
  <head>
    <script src="https://aframe.io/releases/0.7.1/aframe.min.js"></script>
    <script src="https://cdn.rawgit.com/tizzle/aframe-orbit-controls-component/v0.1.14/dist/aframe-orbit-controls-component.min.js"></script>
    <script src="../src/GroundSceneReflector.js"></script>
    <script src="../src/aframe-mirror.js"></script>
</head>

  </head>
  <body>
    <input type="button" value="graphs" onclick="showGraphs([1,2,3], [1,2,3], [1,2,3])">
    <a-scene visible="true" vr-mode-ui="enabled: false">
    <a-entity id="camera" camera="fov:35;near:1" position="0 5 15; user-height:0.5; target:#directionaltarget" orbit-controls="
          target: #target;
          enableDamping: true;
          dampingFactor: 0.125;
          rotateSpeed:0.25;
          rotateToSpeed: 0.04;
          logPosition: false;
          minPolarAngle: 0;        
          maxPolarAngle: 1.43
          enableZoom:true;
          enablePan:false;
          ">
      </a-entity>

      <a-entity id="target" position="0 1 0">
          <a-box id="box" position="-1 -0.25 1" rotation="0 0 0" color="#4CC3D9"></a-box>
          <a-sphere id="sphere" position="0 0 -1" radius="1" color="#EF2D5E"></a-sphere>
          <a-cylinder id="cylinder" position="1 0 1" radius="1" height="1" rotation="0 0 0" color="#FFC65D"></a-cylinder>          
      </a-entity> 
      <a-plane position="0 0 0" rotation="-90 0 0" width=20 height=20 aframe-mirror="color:#848485;intensity:0.4;textureWidth:2048;textureHeight:2048;"></a-plane>
    </a-scene>
  </body>
</html>
```
### THREE.JS example
To use this in threejs is as simple as creating an instance of GroundSceneReflection with the following parameters

```
var gscenereflector = Ashok.GroundSceneReflector(mirrorObj, renderer, scene, data);
```
- ```mirrorObj``` - The mesh to be given the reflector material
- ```renderer``` - Pointer to the renderer instance
- ```scene``` - Pointer to the scene instance
- ```data``` - An object with the named properties and values as mentioned in the above table








