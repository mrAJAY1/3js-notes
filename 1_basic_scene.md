1. What are the things we need to create a basic Scene ?

- To create a basic scene, we need:
  1. A Scene instance.
  2. A Camera instance.
  3. An Object.
  4. A Renderer instance.

2.  What is a Scene?

- A Scene is like a container where we add multiple elements such as objects, lights, cameras etc.
- At some point we ask three js to render the scene to the user.

2. What is an Object?

- An object can be many things.
- It can be :
  - Primitive geometries
  - Imported models
  - Particles
  - Lights
  - Etc.

3. How to create a basic visible Object?

- To create a Visible Object we need to create:

  - A Mesh

    - A mesh in simple words is a combination of geometry(the shape) and a material(how it looks).
      In three js, it is a class representing polygon mesh(vertexes are used to create triangles and then they form polygons)
      vertex-> edge-> face-> surfaces

    ```javascript
    const geometry = new THREE.BoxGeometry(1, 1, 1);
    const material = new THREE.MeshBasicMaterial({ color: 0xff0000 });

    const mesh = new THREE.Mesh(geometry, material);
    ```

    - Here we are `BoxGeometry` is a basic geometry which accepts params - width, height and depth
    - `MeshBasicMaterial` creates a simple material which does not respond to lighting. It is used to create unlit, flat colored surfaces.
    - A material is the properties applied to the surfaces of 3D objects.

4. What is a camera?

- A camera is a simulation of real world camera, which controls the point of view.
- the simplest one is the `PerspectiveCamera`. This is the most realistic camera, simulating the camera of a phone or our eyes.
  >**_NOTE_**:  clipping plane means the region of space visible to the user. here, near clipping plane is the closest the user can view and far clipping plane is the farthest user can view. objects beyond that will not be rendered.

```javascript
// fov in deg, width/height, near clipping plane, far clipping plane.
const camera = new THREE.PerspectiveCamera(75, width / height, 0.1, 1000);
// add the camera to the scene
scene.add(camera);
```
- by default the camera and object will be at the center of the scene, with the object. we need to set the position for the camera and object to be able to make the scene visible as intended.
- We can move the camera and object by adjusting the `position`, `rotation` and the `scale`.
- the `position` is an object that has 3 axis values - `x`,`y` and `z`.
- Vertical Vision Angle(also called fov - field of view). It calculated in degrees. Here it is 75deg

3. What is a renderer?

- Using the renderer is how we render the scene from the camera view
- The results are drawn in to a canvas.
- Three.js will use WebGL to draw the render inside the canvas.
- You can create the canvas yourself or let Three.js do it.
- to render using a render, you pass the scene followed by the camera.
- ```javascript
    const renderer = new THREE.WebGLRenderer({
      // provide the canvas
      canvas:document.querySelector('.canvas');
    })

    // set the width and height for the renderer
    renderer.setSize(width, height);
    renderer.render(scene, camera)
  ```
