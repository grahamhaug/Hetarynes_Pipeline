### 'Plot_Dehydrogenation_Histogram_*.ipynb' - @GCH v1.0 - last updt. 05/11/26

### Notebook Overview:
This directory contains three Jupyter Notebooks for visualizing the distribution of DFT-calculated dehydrogenation energies (ΔE(Arene → Aryne + H₂)) and related strain descriptors across the HAL-8000 dataset:

- `Plot_Dehydrogenation_Histogram_Unified_Fancy.ipynb` — single unified histogram of ΔE across all hetarynes.
- `Plot_Dehydrogenation_Histogram_by_Type.ipynb` — overlaid histograms split by ring size (5- vs 6-membered).
- `Plot_Dehydrogenation_Histogram_Navy_Stately.ipynb` — alternative single-color styling of the unified plot.

Each notebook reads the descriptor-containing .csv files written by Module 7:
- `Aryne_Calculated_Molecular_Descriptors.csv` (all hetarynes)
- `5_membered_Calculated_Molecular_Descriptors.csv`
- `6_membered_Calculated_Molecular_Descriptors.csv`

### Motivation:
Histograms of dehydrogenation energy reveal the thermodynamic accessibility of hetarynes in HAL-8000 — which ring systems are easy to access (low ΔE) versus difficult (high ΔE), and whether 5- vs 6-membered hetarynes show distinct distributions. These histograms are typically the first plots a new student looks at to get a feel for the shape of the dataset before moving on to descriptor correlations or ML modeling.

### How to use these Notebooks:
1. Define the relevant paths to the Module 7 descriptor .csv files in the PATH cell.
2. Run all cells in the notebook.
3. The local directory will contain the resulting `.png` figures.

### Example Outputs:

#### ΔE distribution by ring size:
![energy_by_ring_size](dehydrogenation_energy_histogram_by_ring_size.png)

#### Aryne bond-angle asymmetry by ring size:
![strain_by_ring_size](modulo_bond_angles_histogram_by_ring_size.png)

---

<!-- nav-footer -->
⬅ Previous: [Module 7 — Extract Molecular Descriptors](../../Module7_Extract_DFT_Molecular_Descriptors/README.md)
