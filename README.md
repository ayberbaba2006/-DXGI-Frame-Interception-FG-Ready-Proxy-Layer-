# DXGI Frame Proxy

An **engine-agnostic DXGI proxy layer** that intercepts frame presentation and provides a **safe, extensible foundation** for frame generation and temporal rendering research.

This project focuses on the **hard, often-overlooked part** of modern frame generation systems:  
**reliably entering the rendering pipeline** without breaking stability.

---

## What this is

- A **DXGI / D3D12 proxy** that hooks into the swapchain and presentation flow
- A **robust core architecture** for frame interception
- A **FG-ready pipeline** designed for experimentation and research
- A clean separation between **infrastructure** and **algorithms**

This repository provides the **plumbing**, not the algorithm.

---

## What this is NOT

- ❌ Not a complete Frame Generation implementation  
- ❌ Not a DLSS / FSR replacement  
- ❌ Not a plug-and-play FPS booster  

There is **no frame generation algorithm included** by design.

---

## Why this exists

Most experimental frame generation projects fail not because of bad math, but because of:
- fragile DXGI hooks
- broken device-lost handling
- unsafe Present / ResizeBuffers interception
- race conditions and lifecycle bugs

This project solves **those problems first**.

It is intended as a **research base** that others can build on.

---

## Features

- DXGI swapchain interception
- Safe Present and ResizeBuffers handling
- Device lost / reset resilience
- Thread-safe global state management
- Bypass and enable/disable control paths
- Clean API surface for future FG / temporal algorithms
- Minimal and safe `DllMain` design

---

## Intended use cases

- Frame Generation research
- Temporal rendering experiments
- Optical flow–based approaches
- Engine-agnostic graphics R&D
- Learning how modern FG systems are integrated at a low level

---

## Architecture overview

- **Core**  
  Lifecycle, state machine, safety guarantees

- **DXGI Proxy**  
  Swapchain interception and frame timing access

- **FrameGen Interface**  
  Algorithm-agnostic entry point (no implementation included)

- **Settings & Logging**  
  Thread-safe configuration and diagnostics

The project is structured so that **algorithms can be added without modifying the proxy core**.

---

## Why no FG algorithm?

Because algorithms are:
- subjective
- rapidly evolving
- highly experimental

The infrastructure is the **hard, reusable part**.

If you want to add:
- motion-vector reprojection
- optical flow
- hybrid temporal approaches
- ML-based methods

This project is meant to be the place where you start.

---

## Build status

This project is provided **as-is** and may require platform-specific adjustments depending on your environment.

It is intended for **developers familiar with DXGI / D3D12 internals**.

---

## License

MIT License.

Use it, modify it, build on it.

---

## Disclaimer

This project is for **research and educational purposes**.  
It is not affiliated with NVIDIA, AMD, Intel, or Microsoft.

---

## Final note

If you are looking for a ready-made FPS boost, this is not it.

If you are interested in **how frame generation systems are wired into real rendering pipelines**,  
you are in the right place.
