### Notebook Overview:
Written by @GCH v1.0 - last updt. 05/05/2026

This notebook contains code to perform more project-specific DFT validation and to extract relevant data from validated ORCA 5.0.3 output (.out) files and write output files (ex: .xyz, .sdf) from the DFT-optimized .out files. Once the DFT.out files are validated, extract dE for arenes/arynes and calculate a dE(dehydration) = dE(Arene) ==> dE(Aryne) + dE(H2) in kcal/mol. Outputs a 'Calculated_Dehydration_Energies.csv' to the /Project_dir and prepares files/directories for Featurization/Parameterization. 

### Planned Features:
1. Ensure all methods are commented/have documentation
2. Better Error-Handling/exceptions
3. Fine-tune the cutoffs for bond breaking/formation checks/isomerization

### Motivation:
The "Bacon" notebook is intended to do a strict pass/fail analysis on raw DFT .out files. Bacon will indicate whether a DFT
.out is valid or not (completed successfully, converged to a min., no imaginary freqs) but not if the calculation itself was
actually successful/chemically meaningful for a specific task. Ex: In the current arynes case, it's possible for an aryne to 
break open during optimization. These calculations can converge successfully but are essentially meaningless in the context
of a dataset curation/ML-training task as the calculation itself is invalid. This notebook is a futher layer of validation on
calculations and also is a means of generating accessory files necessary for archival or dataset curation online (.xyz/.sdfs).

### How to Use this Notebook:
1. Define relevant Paths to necessary files in the PATH cell, below.
2. Define relevant output Paths for new files to be written to in the PATH cell, below.
3. Run the notebook from the top-level project directory to process .outs and generate .xyz and .sd-files
4. There are several project-specific cells in this notebook find and exclude any arynes that broke open during optimization
5. Once validated, DFT energies are extracted from .outs and used to calculate dE(dehyd.)
6. An output .csv containing dE(dehyd.) data is written to a loccal dir
7. The final cell will operate on all specified directories to ensure that only validated .outs/.xyzs/sdfs remain for analysis

### Example:
I have a dir with 8760 putatively valid DFT .out files in /Aryne_Orca_DFT_Outputs/ that I've validated using Bacon (or some
equiv software, ex: AQME QCORR). I want to generate an .xyz file containing the optimized molecular geometry for each valid
calculation. I also want to generate an .sd-file (.sdf) for long-term archival, as .sdfs contain connectivity explicitly. I 
run all the cells in this notebook and discover that 66 of my arynes broke open during optimization. Thus at the end of this
process I should have 8694 final .outs, .xyzs, and .sdfs in their respective top level dirs within my .outs dir.

### Program Details
Input: Directories containing Orca 5.0.3 DFT output files (opt+freq; M06-2X-D3 / def2-SVP)

### Validation/GeometryExtraction/File Generation ###
-Extracts optimized .xyz coordinates from Orca 5.0.3 DFT output files and outputs .xyz files to /optimized_xyz_files/
-Uses generated .xyz files to create new .sdf files containing the optimized geometry, output to /Optimized_SDFs/

### Find and remove broken/invalid arynes from the dataset
-For aryne structures, compares the pre/post-opt .sdf files for bond cleavage to ID arynes broken open during optimization
-Removes broken arynes to arynes/success/broken_arynes to remove them from the dataset, output to /Excluded_Aryne_Outs/

### Truncate Dataset to include only entries for "complete" reactions (Arene => Aryne + H2)
- Identifies validated but unpaired .out files in the /success/ dirs that don't form dehydrogenation pairs
- Moves those non-utilized arene/aryne.outs to /excluded subdir within each Arene/Aryne subdirs

### Calclulate dE(dehydrogenation) for remaining pairs
- for any remaining structures, calculate the dE(dehydrogenation) between validated structures
- Output a cleaned .csv file with data pertaining only to validated .out/.sdf/.xyz/RDKit mol structures

### Clean local directories for downstream parameterization 
- Removes any unpaired files to subdirs to ensure a 1:1 match for directory parsing during parameterization
