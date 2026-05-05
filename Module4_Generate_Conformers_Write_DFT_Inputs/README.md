### 'Generate_Conformers_Write_DFT_Inputs.ipynb' - @GCH v1.0 - last updt. 05/04/2026

### Notebook Overview:
This notebook contains code to generate Aryne SMILES strings from Aryne SMILES. A Reaction SMARTS defintion is applied 
to all valid mols extracted from an incoming Pandas DataFrame's 'smiles' column, generating all possible Aryne SMILES. 
The newly minted Aryne SMILES and Aryne_IDs (ex: aryne_12) are appended to a new Pandas DataFrame and written to a an
output .csv file: 'Arenes_and_Generated_Arynes.csv' that is written to the /Module3 directory. 

### Motivation:
A robust and transparent means of generating all possible arynes from a parent aryne. Generate SMILES and prepare for DFT campaign. 

### Planned Features:
1. Remove CSEARCH Dependency (v. slow/better alternatives)
2. Remove QPREP Dependency (doens't handle Paths from super dirs so have to run this notebook from TLD)
3. Improve conformer generation/workflow/variability

### How to Use this Notebook: 
1. Define relevant Paths to output files in the PATH cell below
2. Define DFT Job Parameters
3. Run all cells in the notebook

### Example .sd-file (Following SMILES --> 3D Coord. Conversion):
![sd_file](Example_SDF_Generated.PNG)

### Example DFT Input File (Orca Opt+Freq, Hirshfeld Charges, NBO, MOs):
![Example_Input](Example_DFT_Calc.PNG)

### Bundling DFT Calculations in 100-job Batches:
![Bundling_Calcs](Files_Bundled_for_Submission.PNG)

### Upload Prepared Files/Directories to a SLURM-based HPC:
![Calcs_On_HPC](pORCA_Batch_Directory_Organization.PNG)

### Batch DFT Submission (via pORCA):
![Batch_Submission](pORCA_Batch_Recursion.PNG)

### Processing DFT Outputs (via pORCA):
![Batch_Process](pOrca_Batch_Processing_Directories.PNG)
