# Electric_field_3d_simulation

A browser-based **3D electric field simulator** that visualizes Coulomb interactions between point charges in real time. Place charges on a plane, watch field lines respond, and simulate the motion of mobile charges — all in your browser, no install required.

![License](https://img.shields.io/badge/license-MIT-blue)
![Built With](https://img.shields.io/badge/built%20with-Three.js-black)

## Features

- **3D Field Line Visualization** — Field lines traced via RK4 integration, colored by field strength (blue → green → yellow → red) with directional arrows
- **Flexible Charge Placement** — Place charges on XY, XZ, or YZ planes with adjustable offset, snapped to a 0.5-unit grid
- **Customizable Charges** — Set charge magnitude (±10 μC), mass, and fixed/mobile status per charge
- **Physics Simulation** — Velocity Verlet integration drives mobile charge dynamics with adjustable speed and damping
- **Real-Time Statistics** — Track position, velocity, acceleration, force, kinetic/potential/total energy, and displacement for any mobile charge
- **Particle Trails** — Visualize the trajectory of moving charges with color-gradient trails
- **Interactive Camera** — Orbit (drag), pan (Shift+drag), and zoom (scroll) around the 3D scene

## Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/electric-field-3d.git
   ```
2. Open `electric-field-sim.html` in any modern browser. That's it — no build step, no dependencies to install.

> Three.js (r128) is loaded from a CDN at runtime.

## Usage

| Action | How |
|---|---|
| Place a charge | Select **Place** mode → click on the grid |
| Select a charge | Select **Select** mode → click a charge sphere |
| Move a charge | Select **Move** mode → drag a charge |
| Run simulation | Click **▶ Play** (mobile charges will move under Coulomb forces) |
| Reset simulation | Click **↺ Reset** |
| Orbit camera | Right-click drag (or left-drag in Select/Move mode) |
| Pan camera | Shift + drag or middle-button drag |
| Zoom | Scroll wheel |

## Physics

The simulator computes the superposed electric field from all charges:

$$\vec{E}(\vec{r}) = \sum_i \frac{k q_i}{|\vec{r} - \vec{r}_i|^2} \hat{r}_i$$

Field lines are traced using **4th-order Runge-Kutta** integration. Mobile charge dynamics use **Velocity Verlet** integration with optional velocity-proportional damping for stability.


## Project Structure

```
electric-field-3d/
├── electric-field-sim.html   # Main application (single-file, self-contained)
├── README.md                 # This file
└── LICENSE

```

## Acknowledgments

This project was built with the assistance of **[Claude](https://claude.ai)** (Anthropic). The overall concept, feature requirements, and design direction were provided by Hyeonje Yang; Claude helped generate the implementation code, UI structure, and documentation.

## License

MIT — feel free to use, modify, and share.
