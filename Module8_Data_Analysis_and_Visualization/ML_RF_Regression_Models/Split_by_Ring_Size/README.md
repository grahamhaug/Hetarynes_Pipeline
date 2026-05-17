### 'RF_Regressor_5-Mem_Hetarynes.ipynb' / 'RF_Regressor_6-Mem_Hetarynes.ipynb' - @GCH v1.0 - last updt. 05/11/26

### Notebook Overview:
This directory contains two near-identical Jupyter Notebooks that build Random Forest regression models on Morgan-fingerprint representations of the aryne SMILES — one trained on 5-membered hetarynes only, the other on 6-membered. The models are fit to predict the DFT-calculated dehydrogenation energy ΔE(Arene → Aryne + H₂).

Reads:
- `5_membered_Calculated_Molecular_Descriptors.csv` (Module 7 output)
- `6_membered_Calculated_Molecular_Descriptors.csv` (Module 7 output)

Writes:
- Training/evaluation parity plots (`.png`) to the local directory.

The unified counterpart trained on all hetarynes is in [`../`](../README.md).

### Motivation:
The univariate scatterplots in [`../../Plot_Univariate_Scatterplots/5_vs_6-Membered_Hetarynes/`](../../Plot_Univariate_Scatterplots/5_vs_6-Membered_Hetarynes/README.md) suggest that descriptor–ΔE relationships may differ by ring size. Splitting the RF model by ring size tests whether two specialized models outperform a single unified model, and isolates whether each ring class is independently learnable from fingerprint features alone.

### How to use these Notebooks:
1. Define the relevant paths to the Module 7 descriptor .csv files in the PATH cell.
2. Run all cells in the notebook.
3. The local directory will contain the training/evaluation parity plots as `.png` files.

### Example Output:

#### 5-Membered Hetarynes:
![5-membered_Hets](Baseline_RF_Training_Calc_vs_Pred_5-membered_evaluation.png)

#### 6-Membered Hetarynes:
![6-membered_Hets](Baseline_RF_Training_Calc_vs_Pred_6-membered_evaluation.png)

---

<!-- nav-footer -->
⬅ Previous: [Module 7 — Extract Molecular Descriptors](../../../Module7_Extract_DFT_Molecular_Descriptors/README.md)
