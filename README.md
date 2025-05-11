# Descriptor-factory-X
Descriptor factory X: workflow based on GFN-xTB method calculation, RDKit, and Mordred

**Description:**

This script automates a computational chemistry workflow starting from SMILES:
1. Converts SMILES strings to 3D XYZ coordinates using RDKit. (Parallel)
2. Runs a chain of XTB calculations (opt, scc, vipea, vomega, hess, molden)
   for each generated XYZ structure. (Parallel)
3. Processes the outputs from XTB and the original SMILES in parallel:
    a. Parses XTB single-point like descriptors from the .log file.
    b. Runs Shermo using the .g98.out file (and energy from a temp SCC run)
       to calculate thermodynamic properties.
    c. Runs Multiwfn using the .molden.input file to calculate various
       wavefunction analysis-based descriptors.
    d. Extracts standard molecular descriptors using RDKit from the SMILES.
    e. Extracts a comprehensive set of descriptors using Mordred from the SMILES.
4. Compiles all extracted descriptors into individual CSV files and a final
   merged CSV file.

**Author(s):**

- Weidong Cao, Pinwu Liu/Xi'an Jiaotong University
- wildon0816@163.com

**Date:**

- Last Modified: [2025-05-11]

**Version:**

- [Version 1.0.0]
