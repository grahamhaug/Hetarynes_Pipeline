# Hetarynes_Pipeline
@GCH - Last Updated: 05/11/26 (Added RF Regression Models)

## Project Overview
<div style="text-align: justify;">
The primary motivation of this project is the curation of the "HAL-8000" computational dataset of structures and quantitative molecular descriptors for synthetically accessible heterocylic arynes (hetarynes). The dataset enables data-driven statistical analyses across the range of accessible hetaryne chemical space, furnishing high-level quantitative insights which may allow for both advances in synthetic/methodological development and predictive modeling.
</div>

## Table of Contents:
* [Project Overview](#project-overview)
* [Workflow Description](#workflow-description)

## Workflow Description:
We have developed an easy-to-use and freely available end-to-end workflow in the form of Jupyter Notebooks to:
1. Extract, validate, and deduplicate SMILES strings from multiple .csv datasets
2. Perform SMARTS-based skeletal editing and post-editing structural validation using RDKit (Herein used to retain arene cores)
3. Use Reaction SMARTS to generate all possible hetarynes from parent hetarynes
4. Convert SMILES => 3D coordinates => Orca DFT input files => Batch for HPC Submission/Processing
5. Validate DFT output files, identify and reset failed DFT calculations, and extract energies
6. Extract user-defined quantitative/qualitative molecular descriptors to .csv
7. Peform univariate analysis of extracted descriptors against DFT energies
8. Visualize and analyze the resulting dataset

## The HAL-8000 Dataset:
<div style="text-align: justify;">
The code herein has been used to curate the Heteroaromatic Aryne Library (HAL)-8000. This dataset includes DFT-level structures (M06-2X(D3) / def2-SVP) for 7,143 heterocyclic arenes, 8,116 derived heterocyclic arynes, 8116 DFT-calculated dehydration energies (the energy required to access an aryne, Arene ==> Aryne + H2), and extracted molecular descriptors. DFT-optimized structures are retained as both .xyz and .sdf formats while the tabulated data are retained as .csv files.
</div>

## Motivation:
<div style="text-align: justify;">
Our intention is to release highly generalizable and well-documented code to the broader chemical community. Accordingly, the Jupyter Notebooks in this project are intended to serve as on-the-job training tools for new student orientation/training or for individuals looking to expand their own skillsets. Any helpful suggestions or improvements are welcome, ideally following the guidelines, below.
</div>

## Workflow Design Philosophies:
1. Notebooks should be easy to use regardless of technical background/proficiency.
2. Workflow encourages hands-on/human in-the-loop interaction at key points. 
3. Workflow steps should be completely transparent in purpose and execution.
4. Documentaton/Commenting is a priority to consolidiate knowledge in one source.
5. Notebooks should be modular and readily generalizable to other projects.
6. Notebooks rely on minimal outside dependencies (fewer installs/more robust to external updates).
7. Workflow should be extendable to other Electronic Structure Packages/Levels of Theory/MLIPs.

## Intended Future Features/Updates:
1. More robust conformational searching/handling prior to Orca.inp generation (ex: CREST/GOAT/etc.)
2. Allow for DFT calculations to performed with different levels of theory
3. Additional options for Orca.inp creation for other common job types (scan/TS opt/etc.)
4. Better integration with the pOrca SLURM manager package for iterative submission(s).
5. Expand into MLIP-based workflows
6. Conformational ensembles/analysis

## Schematic of Workflow
I'm going to be a scheme

## Installation and Configuration
env.yml conda blah

## Conda/Env. Dependencies:
tryng to trim more
