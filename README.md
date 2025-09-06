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

## Convention and Units
-------------------
- Distances: Å. Energies: eV. Angles: radians.
- Graphene primitive vectors a1, a2 are defined in the 2D sheet; the CNT chiral
  vector is C_h = n a1 + m a2 and the translation is T = T1 a1 + T2 a2.
- Cylindrical embedding: each 2D lattice coordinate rr is mapped to (θ, z) by
  projecting onto û_C ≡ C_h/|C_h| and û_T ≡ T/|T|.
- Slater–Koster blocks use distance-dependent hoppings and overlaps with
  exponential decays.

External parameters expected to be defined elsewhere
----------------------------------------------------
- Lattice/geometry: 
    r0 : float
        Used as a length scale. If you use r0=2.46 Å (graphene lattice constant),
        a1/a2 will be correct as written. If you use r0=1.42 Å (C–C bond length),
        set a_graphene = sqrt(3)*r0 and use that in a1/a2 instead. Keep it
        consistent across your codebase.
    r_cut : float
        Real-space cutoff (Å) for selecting nearest neighbors.

- SK energy/overlap parameters and decays (all floats):
    Vpp_sigma, Vpp_pi, Vsp_sigma, Vss_sigma
    Vpp_sigma_overlap, Vpp_pi_overlap, Vsp_sigma_overlap, Vss_sigma_overlap
    beta, beta_overlap

- Sampling:
    Nk : int
        Number of k-points along the 1D Brillouin zone.

## Parameters
Key physical parameters for the multi-orbital tight-binding model (for (4,4) CNT, in eV unless stated):
- **Hopping** (from Reich et al., 2004):
  - V_ssσ = -6.8 eV
  - V_spσ = 6.0 eV
  - V_ppσ = 6.4 eV
  - V_ppπ = -2.7 eV
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
  - r_cut = 2.5 Å (maximum distance for nearest-neighbor interactions)
  - s_floor = 10^-6 (overlap matrix floor for Lowdin Orthonormalization)
  - N_k = 500 (number of k-points)
## Contributing
Feedback and contributions are welcome! Please open an issue or submit a pull request for suggestions or improvements, especially for extending the model to other CNT types (e.g., zigzag) or incorporating additional physical effects.
## Contact
For questions or collaboration, please contact [benson7989@gmail.com] or open an issue on GitHub.
