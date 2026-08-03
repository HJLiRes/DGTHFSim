# Molecular Dynamics Simulation Files for 1 M NaPF6 in DG/THF Mixed Electrolytes

## Overview

This repository contains the molecular dynamics (MD) simulation files used in
the study of 1 M NaPF6 electrolytes with different diglyme (DG)/
tetrahydrofuran (THF) molar ratios.

Classical MD simulations were performed using the GROMACS package to
investigate the solvation structures, ion association behaviors, and ion
transport properties of mixed strongly solvating electrolyte (SSE)/weakly
solvating electrolyte (WSE) systems.

By systematically tuning the DG/THF molar ratio, this study reveals the
molecular-level relationship between Na+ solvation structures, ion association
behaviors, and ionic conductivity evolution in mixed SSE/WSE electrolytes.

This repository provides the essential input files required to reproduce the
MD simulations, including force-field parameters, molecular topology files,
GROMACS simulation parameter files, and initial electrolyte configurations.

------------------------------------------------------------------------

## Simulation Systems

Nine electrolyte compositions were investigated with different DG/THF molar
ratios:

| System ID  | DG/THF molar ratio |
|------------|--------------------|
| DG_THF_0_1 | 0/1 |
| DG_THF_1_8 | 1/8 |
| DG_THF_1_6 | 1/6 |
| DG_THF_1_4 | 1/4 |
| DG_THF_1_3 | 1/3 |
| DG_THF_1_2 | 1/2 |
| DG_THF_1_1 | 1/1 |
| DG_THF_2_1 | 2/1 |
| DG_THF_1_0 | 1/0 |

All systems correspond to 1 M NaPF6 electrolytes.

For each electrolyte composition, five independent simulations were performed
using different initial configurations to obtain statistically reliable results.

The initial configurations for independent simulations are provided as:
`systems/*/confout_*.gro`

------------------------------------------------------------------------

## Repository Structure and File Description

| File/Directory            | Description               |
|---------------------------|---------------------------|
| `force_field/`            | Force-field parameter files used in MD simulations |
| `force_field/DG.itp`      | Molecular topology file for diglyme (DG) |
| `force_field/THF.itp`     | Molecular topology file for tetrahydrofuran (THF) |
| `force_field/PF6-.itp`    | Molecular topology file for PF6- |
| `force_field/Na+.itp`     | Molecular topology file for Na+ |
| `mdp/mdout.mdp`           | GROMACS parameter file for MD production simulations |
| `systems/`                | Initial configurations and topology files for all electrolyte systems |
| `systems/*/confout_*.gro` | Initial configuration for five independent simulations |
| `systems/*/topol.top`     | GROMACS topology files defining system compositions and interactions |
| `systems/*/nonbond.itp`   | Nonbonded interaction parameters |
| `README.md`               | Description of the repository and file organization |

------------------------------------------------------------------------

## Reproduction of NVT Production Simulations

A typical simulation can be prepared using the following GROMACS command:

```bash
gmx grompp \
-f mdout.mdp \
-c confout_*.gro \
-p topol.top \
-o md.tpr
```

The simulation can then be performed using:

```bash
gmx mdrun -s md.tpr
```
Before running the simulations, ensure that all required force-field files are
correctly located and referenced in the topology files.

The provided files allow reproduction of the MD simulations reported in this
study.

------------------------------------------------------------------------

## Data Availability

All data supporting the findings of this study are available in the article and
its Supporting Information.

The GROMACS simulation files used in this study, including force-field
parameters, topology files, simulation parameter files, and initial
configurations, are openly available in this repository.

------------------------------------------------------------------------

## Citation

If you use the simulation files provided in this repository, please cite:

Authors:
Hongjin Li, Tao Wang, Shu Li, Tianying Yan

Title:
The Effects of Strongly and Weakly Solvating Electrolytes on Ionic Conductivity in Sodium-Ion Battery Electrolytes

Journal:

Year:

DOI:



