# Interactive 3D Black Hole Simulation 🌌

![Screen Recording 2025-06-04 at 11 54 43 PM](https://github.com/user-attachments/assets/0f8bc6c0-e884-4524-824d-1997e4532f7d)


Welcome to the Interactive 3D Black Hole Simulation! This project leverages the power of Three.js to create a visually engaging and highly customizable representation of a black hole, complete with a dynamic accretion disk, a glowing event horizon, and an immersive deep-space background.

Go here: [https://black-hole-sim-theta.vercel.app/](https://black-hole-sim-theta.vercel.app/) 

## ✨ Key Features

* **Interactive Black Hole:** A central, visually prominent black hole entity.
* **Dynamic Accretion Disk:** Simulated using an intricate particle system. You can customize its colors, particle speed, and overall shape as particles spiral inwards.
* **Glowing Event Horizon:** A distinct torus shape vividly visualizes the critical boundary around the black hole's point of no return.
* **Immersive Deep Space Background:**
    * **Distant Starfield:** A particle system generates a vast expanse of distant stars.
    * **Procedural Nebulae & Galaxies:** Particle-based nebulae and distant galaxies are generated on-the-fly, adding depth and a sense of cosmic scale.
* **Advanced Post-Processing Effects:**
    * **Bloom:** Adds a luminous, ethereal glow to bright elements like the event horizon and accretion disk particles.
    * **Scanlines & Grain:** Optional retro or cinematic visual effects to enhance the mood.
* **Real-time Customization:** An interactive GUI (dat.GUI) allows you to tweak numerous simulation parameters on the fly for immediate visual feedback.
* **Reset Functionality:** Easily revert all settings to their initial, carefully designed default state.
* **Fullscreen Mode:** Immerse yourself completely in the cosmic spectacle.

## 🛠️ Technologies Used

* **HTML5:** For the basic page structure.
* **CSS3:** For minimal page styling.
* **JavaScript (ES6 Modules):** The core language for interactivity and logic.
* **Three.js (r136):** A powerful 3D graphics library that renders the scene in WebGL.
* **dat.GUI:** A lightweight library for creating the interactive control panel.

## 🚀 Accessing the Simulation

This project is designed for easy access and direct interaction in your browser.

* **Live (thanks to Vercel for the compute):**
    * **Go here: [https://black-hole-sim-theta.vercel.app/](https://black-hole-sim-theta.vercel.app/) 

* **Running Locally (for Development/Modification):**
    **Clone the Repository (or Download the Files):**

## 🏗️ Project Structure

The entire simulation is encapsulated within a single `index.html` file. This strategic choice makes it highly portable and easy to understand. The file includes:
* The HTML document structure.
* Embedded CSS for styling the page elements.
* All JavaScript code, which utilizes ES6 modules to import Three.js and dat.GUI directly from Content Delivery Networks (CDNs).

## 🎓 Educational Aspects & Key Concepts

This simulation serves as a practical demonstration of several core concepts in 3D web graphics using Three.js:

* **Scene Setup:** Illustrates the initialization of fundamental Three.js components: `THREE.Scene` (the container for all objects), `THREE.PerspectiveCamera` (the viewpoint into the scene), and `THREE.WebGLRenderer` (which draws the scene).
* **Geometries & Materials:**
    * `THREE.SphereGeometry`: Forms the central black hole, rendered with a black `MeshBasicMaterial`.
    * `THREE.TorusGeometry`: Creates the glowing event horizon, using an emissive `MeshBasicMaterial`.
    * `THREE.Points` with `THREE.BufferGeometry`: This combination is the workhorse for rendering large numbers of particles efficiently. It's used for:
        * The **accretion disk:** Thousands of individually colored and positioned particles.
        * The **distant starfield:** Simulating a vast number of stars.
        * **Particle-based nebulae and galaxies:** Layering particle clouds to create a volumetric illusion.
    * `THREE.PointsMaterial`: Applied to all particle systems, offering control over particle size, color (vertex colors), and blending modes.
* **Particle Systems:** Multiple particle systems are employed to achieve dynamic and diffuse visual effects. The accretion disk particles are animated with custom logic to spiral inwards. The background elements (stars, nebulae, galaxies) are also rendered as particles, providing a performant method for complex cosmic scenery.
* **Procedural Sprite Textures:** To make particles appear as soft, circular "photons" or diffuse cloud elements (rather than default squares), `THREE.CanvasTexture` is used. Textures are generated on-the-fly using the HTML5 2D Canvas API, then applied to the `map` property of `PointsMaterial`. This technique avoids reliance on external image files for these sprites.
* **Post-Processing Pipeline:**
    * `THREE.EffectComposer`: Manages a sequence of post-processing passes, allowing for advanced visual effects to be layered onto the rendered scene.
    * `UnrealBloomPass`: Creates a realistic and configurable glow effect around bright objects, essential for the luminosity of the event horizon, accretion disk, and other celestial phenomena.
    * `ShaderPass`: Used with custom GLSL shader code (embedded as JavaScript strings) to implement effects like scanlines and film grain, adding to the simulation's stylistic options.
* **Interactivity & Animation:**
    * `OrbitControls`: Provides intuitive mouse-based camera manipulation (rotate, pan, zoom).
    * `dat.GUI`: Offers a simple yet powerful interface for modifying a wide array of simulation parameters in real-time.
    * `requestAnimationFrame`: The browser's API for creating a smooth, optimized animation loop. Object properties (like particle positions) and shader uniforms (like `time` for animated effects) are updated each frame.

## 🔧 Customization

* **GUI Controls:** The "Open Controls" panel is the primary way to customize the simulation live. Experiment with colors, sizes, speeds, particle densities, and effect intensities to create your desired cosmic scene.
* **`initialParams` Object:** For more permanent adjustments to the default appearance, you can modify the `initialParams` object directly within the JavaScript code in `index.html`.
* **Procedural Texture Functions:** Delve into functions like `createAccretionParticleSprite()`, `createNebulaGalaxySprite()`, `createDustCloudTexture()`, and `createDistantGalaxyTexture()` to alter the fundamental appearance of the generated sprites and textures.

## 💡 Future Enhancements (Ideas)

* Develop a more physically-based accretion disk shader for realistic differential rotation and temperature gradients.
* Implement a gravitational lensing post-processing shader for a more accurate visual representation of light bending around the black hole.
* Add functionality to allow users to load their own custom image textures for background nebulae and galaxies.
* Introduce a wider variety of celestial body types and procedural generation algorithms for the background.
* Further optimize particle systems to support even larger numbers of particles for richer scenes.

## 📄 License

This work is licensed under the **Creative Commons Attribution-NonCommercial 4.0 International License (CC BY-NC 4.0)**.

You are free to:
* **Share** — copy and redistribute the material in any medium or format
* **Adapt** — remix, transform, and build upon the material

Under the following terms:
* **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made.
* **NonCommercial** — You may not use the material for commercial purposes.

[Learn more about CC BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/)

Developed and maintained by [Sai Gattupalli](https://gattupalli.com), College of Education, University of Massachusetts Amherst.

---

Enjoy exploring the cosmos! 🌠
