# CS330-3D-Scene
A lightweight C++/OpenGL demo that builds a “bee in the garden” 3D scene from scratch—complete with textured ground, trees, leaves and props—using a modular scene manager, custom shaders, and tag-based resource handling to teach real-time rendering and software design fundamentals.

---

## Table of Contents

1. [Design Philosophy](#design-philosophy)  
2. [Development Workflow](#development-workflow)  
3. [Iteration & Evolution](#iteration--evolution)  
4. [Computer Science & My Goals](#computer-science--my-goals)  
5. [Future Pathways](#future-pathways)  

---

## Design Philosophy

### How I approach designing software  
I start by breaking the scene down into its core objects (ground, backdrop, hive, leaves, props). From there I define a small set of reusable abstractions—mesh loaders, shader managers, texture collections—and sketch out the data flow (e.g., how transforms, materials, and textures get sent to the GPU).  

### New design skills I’ve crafted  
- **Modular scene graph:** I learned to isolate object-specific logic (e.g., `RenderTree()`, `RenderPipe()`) from shared plumbing (e.g., `SetTransformations()`).  
- **Tag-based resource lookup:** Storing textures and materials by tag simplified swapping and reusing assets.  
- **Configurable lighting pipeline:** I architected a flexible system to push multiple light sources (directional, point, spot) into GLSL.

### My design process  
1. **Concept sketch:** Outline all scene elements on paper.  
2. **Core abstractions:** Build `ShapeMeshes`, `ShaderManager`, and `SceneManager` shells.  
3. **Incremental feature adds:** Load one mesh + texture at a time, verify on screen.  
4. **Refinement:** Extract common patterns (e.g., transform & shader calls) into shared methods.

### Applying these tactics in future work  
- I’ll continue starting every new graphics feature with a minimal proof-of-concept, then refactor common code into reusable utilities.  
- Tag-based resource management will carry over into larger engines or tools.

---

## Development Workflow

### How I approach developing programs  
I favor a **feature-driven** approach: pick one visible thing (like the ground), implement it from data load → shader uniforms → draw call, then move on.  

### New development strategies used  
- **GLM transforms in C++:** Mastered chaining `translate`, `rotate`, and `scale` into a single model-view matrix.  
- **Texture array binding:** Learned how to bind multiple textures to different texture units and pass sampler slots into GLSL.

### How iteration factored into my development  
Every milestone ended in a working screenshot. I’d merge the latest “two-texture blend” or “leaf cluster” only after it passed visual smoke tests, then refactor. Frequent commits ensured I had clean rollback points whenever a change broke rendering.

### Evolving my approach over milestones  
- **Milestone 1:** Hard-coded transforms, no abstraction.  
- **Milestone 2:** Pulled out `SetTransformations()` and centralized shader setup.  
- **Milestone 3:** Introduced material/tag lookup and UV scaling controls—finalizing a clean, maintainable codebase.

---

## Computer Science & My Goals

This project reinforces core CS skills—data abstraction, resource management, and linear algebra—that directly support my goal of becoming a graphics/engine developer. Writing my own shader manager and scene graph deepens my understanding of GPU pipelines and real-time rendering.

---

## Future Pathways

### Educational Pathway  
- **Advanced graphics courses:** I can now tackle ray-tracing and GPU compute demos more confidently.  
- **Research readiness:** The fundamentals I’ve built position me to explore procedural generation or VR coursework.

### Professional Pathway  
- **Engine integration:** I can contribute custom rendering modules in a game engine or visualization toolchain.  
- **Pipeline tooling:** Experience with tag-based assets and shader uniforms translates to building content-creation pipelines for studios.
