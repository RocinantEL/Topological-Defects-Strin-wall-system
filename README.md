# 2D String-Wall System Dynamics in Quantum Field Theory

Numerical simulation of topological defects—specifically cosmic strings (vortices) bounded by axionic domain walls—in a 2D complex scalar field theory with spontaneous and explicit $U(1)$ symmetry breaking on a periodic lattice (2D torus).

## Physical Model

We consider a classical $(2+1)$-dimensional complex scalar field $\phi(x, y, t) = \phi_1 + i\phi_2$ governed by a Mexican-hat (Higgs) potential with an explicit $U(1)$ symmetry-breaking term:

$$V(\phi) = \frac{\lambda^2}{4}\left(\vert{}\phi\vert{}^2 - \eta^2\right)^2 - \frac{m^3}{2\eta}\left(\phi + \phi^*\right)$$

where:
- $\eta = 1.0$ is the vacuum expectation value (VEV),
- $\lambda = 2.0$ controls the spontaneous $U(1)$ symmetry-breaking scale (vortex core size),
- $m = 0.15$ controls the explicit symmetry-breaking scale (domain wall thickness and tension).

The resulting equations of motion on a discrete 2D lattice with spatial coupling $J = 1.0$ are:

$$\ddot{\phi}_1 = J \nabla^2 \phi_1 - \lambda^2 \phi_1 \left(\vert{}\phi\vert{}^2 - \eta^2\right) + \frac{m^3}{\eta}$$

$$\ddot{\phi}_2 = J \nabla^2 \phi_2 - \lambda^2 \phi_2 \left(\vert{}\phi\vert{}^2 - \eta^2\right)$$

## Simulated Configurations

1. **Vortex–Antivortex Pair ($Q_{\text{total}} = +1 - 1 = 0$):**
   - Static phase map and 1D kink profile across the domain wall connecting the vortex and antivortex cores.
   - Real-time evolution showing domain wall formation, tension-driven attraction, and dynamics.
2. **Three-Vortex System on a Torus ($Q_{\text{total}} = +1 - 1 + 1 = +1$):**
   - Vectorized multi-vortex ansatz with periodic phase wrapping into $[-\pi, \pi]$.
   - Time evolution of domain walls and topological defect interactions under periodic boundary conditions.

## Numerical Method

- **Grid:** $150 \times 150$ 2D square lattice with periodic boundary conditions (implemented via `np.roll` for the discrete 5-point Laplacian).
- **Time Integration:** Semi-implicit (symplectic) Euler scheme with $\Delta t = 0.04$ and 30 sub-steps per animation frame.
- **Visualization:** Dual-panel phase heatmaps (`twilight` colormap) and 2D vector field quiver plots.

## Repository Structure

```text
.
├── string_wall_simulation.ipynb   # Vortex-antivortex & 3-vortex simulations and visualizations
├── requirements.txt               # Python dependencies
└── README.md
