# 3D Path Tracing Showcase

A real-time, single-file WebGL2 3D path tracer featuring a 4-room environment, an interactive water pool, spatial culling, and physics-based object manipulation.

## Features

- **Real-Time WebGL2 Path Tracing:** Progressive accumulation rendering using `RGBA32F` floating-point framebuffers.
- **Multi-Room Scene & Water Pool:** 4 interconnected rooms with a reflective/refractive water pool and room-based culling optimization.
- **Interactive Physics & Props:** Pick up, carry, throw, drop, and reset scene objects (spheres and lamps) in real time.
- **Dynamic Lighting:** Toggleable player flashlight (`F`) alongside emissive scene light sources.
- **Resilient GPU Initialization:**
  - Multi-pass WebGL2 context fallback with canvas cloning.
  - `RGBA32F` framebuffer completeness verification with driver diagnostics.
  - Non-blocking asynchronous shader compilation via `KHR_parallel_shader_compile` with timeout safeguards.
- **Live Telemetry Overlay:** Displays real-time FPS, accumulated sample count, water visibility state, flashlight status, and active GPU renderer info.

## Controls

| Key / Input | Action |
| :--- | :--- |
| **Click** | Lock mouse pointer (look around) |
| **W A S D** | Move |
| **Space** | Jump |
| **F** | Toggle flashlight |
| **Left Click (LMB)** | Grab / Throw sphere or lamp |
| **E** | Drop held object |
| **R** | Reset all objects to initial positions |
| **ESC** | Release mouse pointer |

## Quick Start

No build step, bundler, or local server is required:

1. Clone the repository or download `pathtracing.html`.
2. Open `pathtracing.html` directly in any modern WebGL2-capable browser (Chrome, Edge, or Firefox) with hardware acceleration enabled.

## Technical Notes

- **Zero Dependencies:** Entire engine, GLSL shaders, scene geometry, and UI are self-contained inside `pathtracing.html`.
- **Browser Requirements:** Requires WebGL2 support and the `EXT_color_buffer_float` extension for high-precision `RGBA32F` progressive accumulation.

---

*Autonomously initialized and authored by `claude-agent-foxvuk` (Claude Opus 5.5) as an experimental real-time graphics sandbox.*
