# Hetarynes_Pipeline
@GCH - Last Updated: 05/10/26

### Project Description:
The primary motivation of this project is the curation of a computational dataset of structures and quantitative molecular
descriptors for synthetically accessible heterocylic arynes (hetarynes). The dataset will enable data-driven statistical 
analyses across the range of accessible hetaryne chemical space, furnishing high-level quantitative insights which may allow
for both advances in synthetic/methodological development and predictive modeling. 

Additionally, we have developed an easy-to-use and freely available end-to-end workflow in the form of Jupyter Notebooks to:
1. Extract, validate, and deduplicate SMILES strings from multiple .csv datasets
2. Perform SMARTS-based skeletal editing and post-editing structural validation using RDKit (Herein used to retain arene cores)
3. Use Reaction SMARTS to generate all possible hetarynes from parent hetarynes
4. Convert SMILES => 3D coordinates => Orca DFT input files => Batch for HPC Submission/Processing
5. Validate DFT output files, identify and reset failed DFT calculations, and extract energies
6. Extract user-defined quantitative/qualitative molecular descriptors to .csv
7. Peform univariate analysis of extracted descriptors against DFT energies
8. Visualize and analyze the resulting data

### Workflow/Coding Motivation and Philosophy:
1. Notebooks should be easy to use regardless of technical background/proficiency.
2. Workflow encourages hands-on/human in-the-loop interaction at key points. 
3. Workflow steps should be completely transparent in purpose and execution.
4. Documentaton/Commenting is a priority to consolidiate knowledge in one source.
5. Notebooks should be modular and readily generalizable to other projects.
6. Notebooks rely on minimal outside dependencies (fewer installs/more robust to external updates).
7. Workflow should be extendable to other Electronic Structure Packages/Levels of Theory/MLIPs.

### Intended Future Features/Updates:
1. More robust conformational searching/handling prior to Orca.inp generation (ex: CREST/GOAT/etc.)
2. Allow for DFT calculations to performed with different levels of theory
3. Additional options for Orca.inp creation for other common job types (scan/TS opt/etc.)
4. Better integration with the pOrca SLURM manager package for iterative submission(s).
5. Expand into MLIP-based workflows
6. Conformational ensembles/analysis

### Schematic of Workflow
I'm going to be a scheme

### Installation and Configuration
env.yml conda blah

### Conda/Env. Dependencies:
tryng to trim more
