# hopf
🧣 A graphical program for exploring the Hopf fibration.

<p align="center">
  <img src="https://github.com/mwalczyk/hopf/blob/master/screenshots/fibration.png" alt="screenshot" width="400" height="auto"/>
</p>

## Description
The Hopf fibration is a mapping from S3 to S2 discovered by Heinz Hopf in 1931. Confusingly, S3 actually refers to the sphere (or hypersphere) in 4D space. Similarly, S2 refers to the sphere that we are most familiar with in 3D space. To quote Wikipedia: "Hopf found a many-to-one continuous function (or 'map') from the 3-sphere onto the 2-sphere such that each distinct point of the 2-sphere is mapped to from a distinct great circle of the 3-sphere."

A "great circle" is essentially a planar "slice" of a sphere that passes through its center. It is difficult to visualize what a great circle on the surface of a 4-dimensional sphere looks like, but luckily, we don't have to. Each of these great circles in the domain of the mapping function forms a "fiber" that we can project down to 3-space. Doing so results in a beautiful structure of nested shapes that appear to be intricately woven together.

How does the mapping work?

## Tested On
- Windows 10
- NVIDIA GeForce GTX 1660 Ti

NOTE: this project will only run on graphics cards that support OpenGL [Direct State Access](https://www.khronos.org/opengl/wiki/Direct_State_Access) (DSA).

## To Build
1. Clone this repo and initialize submodules: 
```shell
git submodule init
git submodule update
```
2. From the root directory, run the following commands:
```shell
mkdir build
cd build
cmake ..
```
3. Open the project file for your IDE of choice (generated above)
4. Build and run the project

## To Use
Upon launching the application, you should see three separate UI panels labeled:

- `Hopf Fibration`: contains all of the primary controls, mode selection, etc.
- `Mapping (Points on S2)`: visualizes the current codomain (see notes below)
- `Appearance and Export`: contains some basic settings for adjusting the appearance of the model as well as a button for .obj export

Within the panel labeled `Hopf Fibration`, there are several "mapping modes" available, each of which corresponds to a (configurable) set of points on the surface of S2 that form the codomain of the mapping:

- `Great Circle`: sets the codomain to the set of points formed by one or more great circles on the surfaces of S2
- `Random`: sets the codomain to a randomly distributed set of points on the surface of S2
- `Loxodrome`: sets the codomain to a [Rhumb line](https://en.wikipedia.org/wiki/Rhumb_line) (spiral arc) on the surface of S2
- `Curl`: sets the codomain to a curled, floral pattern on the surface of S2

The four different modes are shown below:

<p align="center">
  <img src="https://github.com/mwalczyk/hopf/blob/master/screenshots/mode_great_circle.png" alt="screenshot" width="200" height="auto"/>
  <img src="https://github.com/mwalczyk/hopf/blob/master/screenshots/mode_random.png" alt="screenshot" width="200" height="auto"/>
  <img src="https://github.com/mwalczyk/hopf/blob/master/screenshots/mode_loxodrome.png" alt="screenshot" width="200" height="auto"/>
  <img src="https://github.com/mwalczyk/hopf/blob/master/screenshots/mode_curl.png" alt="screenshot" width="200" height="auto"/>
</p>

You can use your mouse to rotate the model in space. You can zoom in or out with your scroll wheel. Finally, you can "home" (i.e. reset) the current view by pressing `h` on your keyboard.

## To Do
- [ ] Clean up the `Mesh` class (maybe create a separate `Renderer` class?)
- [ ] Research ways of generating the topology directly on the GPU (compute shaders?)
- [ ] Figure out path guided extrusion
- [ ] Add path tracing (long-term)

## Credits
This project was largely inspired by and based on previous work done by [Dr. Niles Johnson](https://nilesjohnson.net/), who teaches at Ohio State University. In particular, I used his parameterization of the fibers, as outlined in his [production](https://nilesjohnson.net/hopf-production.html) notes. His animated videos of the Hopf fibration are what motivated me to delve into this topic.

Other resources that were helpful during the creation of this project:
- [Wikipedia Article on the Hopf Fibration](https://en.wikipedia.org/wiki/Hopf_fibration)
- [Explanation of Quaternions by Ken Shoemake](https://nilesjohnson.net/hopf-articles/Shoemake_quatut.pdf)
- [A Young Person's Guide to the Hopf Fibration](https://arxiv.org/abs/0908.1205)
- [An Elementary Introduction to the Hopf Fibration](https://nilesjohnson.net/hopf-articles/Lyons_Elem-intro-Hopf-fibration.pdf)

The shadow mapping code (and many other OpenGL tips) were largely adapted from [learnopengl.com](https://learnopengl.com), an amazing resource for anyone trying to learn more about the OpenGL API and computer graphics.

### License
[Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/)
