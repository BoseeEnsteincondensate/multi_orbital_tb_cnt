# Multi-Orbital Tight-Binding Model for Armchair Carbon Nanotubes

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

A Python implementation of a multi-orbital tight-binding model for armchair carbon nanotubes (CNTs), focusing on non-orthogonal effects and curvature-induced σ-π hybridization. This code achieves band gap predictions with errors <1% compared to DFT-GGA benchmarks for chiralities from (4,4) to (10,10), as detailed in our associated research paper. It computes band structures and density of states (DOS) using the Slater-Koster method and Löwdin orthogonalization.

## Features
- Generates CNT geometry from a graphene lattice for armchair CNTs with chirality (n,n).
- Constructs Hamiltonian and overlap matrices incorporating non-orthogonal effects.
- Computes band structures and projected DOS for s, p_x, p_y, p_z orbitals.
- Optimized parameters (β, β_overlap) ensure high accuracy and computational efficiency.
- Visualizes results with publication-quality plots (e.g., band structures and PDOS).

## Prerequisites
- Python 3.8 or higher
- Required packages: `numpy`, `scipy`, `matplotlib`

## Parameters
Key physical parameters for the multi-orbital tight-binding model (for (4,4) CNT, in eV unless stated):
- **Hopping** (from Reich et al., 2004):
  - V_ssσ = -6.8
  - V_spσ = 6.0
  - V_ppσ = 6.4
  - V_ppπ = -2.7
- **Overlap** (from Popov and Henrard, 2004, dimensionless):
  - s_ssσ = -0.2
  - s_spσ = 0.1
  - s_ppσ = 0.2
  - s_ppπ = -0.05
- **Decay**:
  - β = 4.46
  - β_overlap = 2.85
- **Geometry**:
  - r0 = 1.42 Å (equilibrium carbon-carbon bond length)
  - max_dist = 2.5 Å (maximum distance for nearest-neighbor interactions)
  - r_ref = np.sqrt(3) * r0 Å (reference distance for lattice calculations)
## Contributing
Feedback and contributions are welcome! Please open an issue or submit a pull request for suggestions or improvements, especially for extending the model to other CNT types (e.g., zigzag) or incorporating additional physical effects.
## Contact
For questions or collaboration, please contact [benson7989@gmail.com] or open an issue on GitHub.
