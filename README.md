# 3D Path Tracing Showcase

A real-time, single-file WebGL2 3D path tracer featuring a 4-room environment, a physically simulated GPU wave pool, buoyancy physics, spatial culling, and NaN-resistant progressive accumulation.

## Features

- **Real-Time WebGL2 Path Tracing:** Progressive accumulation rendering using `RGBA32F` floating-point framebuffers with NaN propagation safeguards in the post-processing denoiser.
- **GPU Heightfield Wave Simulation:** 160x220 2D wave-equation solver (`8m × 11m` pool) with boundary wave reflection, swimmer wakes, and dynamic splashes from thrown objects.
- **Physical Water Optics:** Real wave-derived surface normals, Laplacian-based caustic light focusing, Beer-Lambert depth absorption, and foam rendering.
- **Swimming & Buoyancy Physics:** Full player swimming and diving mechanics alongside density-based buoyancy for floating objects (spheres and lamps).
- **Interactive Physics & Props:** Pick up, carry, throw, drop, and reset scene objects in real time while preserving active water ripples.
- **Dynamic Lighting:** Toggleable player flashlight (`F`) alongside emissive scene light sources.
- **Resilient GPU Initialization:**
  - Multi-pass WebGL2 context fallback with canvas cloning.
  - `RGBA32F` framebuffer completeness verification with driver diagnostics.
  - Non-blocking asynchronous shader compilation via `KHR_parallel_shader_compile` with timeout safeguards.
- **Live Telemetry Overlay:** Displays real-time FPS, accumulated sample count, water ripple activity state, flashlight status, and active GPU renderer info.

## Controls

| Key / Input | Action |
| :--- | :--- |
| **Click** | Lock mouse pointer (look around) |
| **W A S D** | Move / Swim (press **W** near pool edge to climb out) |
| **Space** | Jump / Swim up |
| **C** | Dive underwater |
| **F** | Toggle flashlight |
| **Left Click (LMB)** | Grab / Throw sphere or lamp |
| **E** | Drop held object |
| **R** | Reset object positions (preserves water waves) |
| **ESC** | Release mouse pointer |

## Quick Start

No build step, bundler, or local server is required:

1. Clone the repository or download `pathtracing.html`.
2. Open `pathtracing.html` directly in any modern WebGL2-capable browser (Chrome, Edge, or Firefox) with hardware acceleration enabled.

## Technical Notes

- **Zero Dependencies:** Entire engine, wave-equation shader, path-tracing GLSL shaders, scene geometry, and UI are self-contained inside `pathtracing.html`.
- **Browser Requirements:** Requires WebGL2 support and the `EXT_color_buffer_float` extension for high-precision `RGBA32F` progressive accumulation.

---

*Autonomously initialized and authored by `claude-agent-foxvuk` (Claude Opus 5.5) as an experimental real-time graphics sandbox.*
