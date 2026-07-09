# Out-Sphere-Trap
All processed datasets required to replicate the statistical claims in the manuscript "The Artificial Outer-Sphere Trap: Unmasking the Ionic Strength Artifact in Classical Molecular Dynamics of Oxyanion Adsorption."

# The Artificial Outer-Sphere Trap: Molecular Dynamics Artifacts in Oxyanion Adsorption

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![MDAnalysis](https://img.shields.io/badge/MDAnalysis-2.6+-green.svg)](https://www.mdanalysis.org/)

This repository contains the dataset, simulation templates, and custom Python analysis scripts for the manuscript:

> **"The Artificial Outer-Sphere Trap: Unmasking the Ionic Strength Artifact in Classical Molecular Dynamics of Oxyanion Adsorption"**

## Overview

This project systematically evaluates the topological and thermodynamic validity of classical non-reactive molecular dynamics (using the CLAYFF framework) for simulating specific adsorption (chemisorption) of oxyanions (As(V) and F⁻) onto iron oxide surfaces ($\alpha$-Fe₂O₃ and Fe₃O₄). 

Through a high-throughput computational matrix of 36 simulated environments, we demonstrate that classical potentials consistently fail to breach the ~3.5 Å interfacial threshold required for covalent ligand exchange. This confines the ions in an **"artificial outer-sphere trap"**, leading to an unphysical hypersensitivity to background salinity (Electrical Double Layer compression).

## Repository Structure

* `1_LAMMPS_Inputs/`: Contains the baseline input scripts (`in.adsorption_template`) and the `forcefield.params` used to run the molecular dynamics simulations in LAMMPS.
* `2_Python_Analysis/`: Contains the custom Python scripts used for trajectory processing and statistical visualization.
  * `analisis_descriptores_2.py`: Parses LAMMPS `.dump` files to calculate equilibrium distances, hydration numbers, interfacial residence times, and axial density profiles ($\rho(z)$).
  * `generador_figuras_jcis.py`: Generates publication-quality Q1 figures (Boxplots, Lineplots, Pearson Correlation Heatmaps, and PCA clustering ellipses) using `scikit-learn` and `seaborn`.
* `3_Dataset/`: Contains `Metricas_Termodinamicas_Globales.csv`, the extracted thermodynamic descriptors for all 36 simulated systems.


## Prerequisites & Installation

To run the analysis scripts and reproduce the figures, you need Python 3.8 or higher. We recommend creating a virtual environment. Install the required dependencies using the provided `requirements.txt` file:


# Clone the repository
git clone [https://github.com/JMOlaguez/Outer-Sphere-Trap.git](https://github.com/JMOlaguez/Outer-Sphere-Trap.git)
cd Outer-Sphere-Trap-MD

# Install dependencies
pip install -r requirements.txt
