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
    * Primitive geometries
    * Imported models
    * Particles
    * Lights 
    * Etc.

3. How to create a basic visible Object?
- To create a Visible Object we need to create:
    1. A Mesh
        - A mesh in simple words is a combination of geometry(the shape) and a material(how it looks).
        In three js, it is a class representing polygon mesh(vertexes are used to create triangles and then they form polygons)
        vertex-> edge-> face-> surfaces
         