# Molecular Dynamics Simulation Input Files for 1 M NaPF6 in DG/THF Electrolytes

## Overview

This repository contains the molecular dynamics (MD) simulation input files
used in the study of 1 M NaPF6 electrolytes with various diglyme (DG)/
tetrahydrofuran (THF) molar ratios.

Classical molecular dynamics simulations were performed using the GROMACS 
package to investigate the solvation structures, ion association behaviors, 
and ion transport properties of mixed strongly solvating electrolyte (SSE)/
weakly solvating electrolyte (WSE) systems.

The repository provides the essential input files required to reproduce the
NVT production simulations, including force-field parameters, molecular
topologies files, simulation parameters files, and initial configurations.

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

For each electrolyte composition, five independent NVT production simulations
were performed using different initial configurations to obtain statistically
reliable averaged values and standard deviations.

Each independent simulation contains a corresponding initial configuration 
file (`systems/*/confout_*.gro`).

------------------------------------------------------------------------

## Simulation Protocol

All molecular dynamics simulations were performed using the GROMACS package.

The NVT production simulations were conducted using the GROMACS parameter file:
`mdp/mdout.mdp`

Identical force-field parameters and simulation settings were applied to all 
electrolyte compositions to ensure consistent comparison among different 
DG/THF systems.

The simulation inputs provided in this repository include:

- Molecular force-field parameters
- Topology definitions
- Nonbonded interaction parameters
- GROMACS simulation parameters
- Initial molecular configurations

These files allow direct reproduction of the NVT production simulations 
reported in this study.

------------------------------------------------------------------------

## Repository Structure and File Description

| File/Directory            | Description               |
|---------------------------|---------------------------|
| `force_field/`            | Force-field parameter files used for corresponding electrolyte systems. |
| `force_field/DG.itp`      | Molecular topology file for DG. |
| `force_field/THF.itp`     | Molecular topology file for THF. |
| `force_field/PF6-.itp`    | Molecular topology file for PF6-. |
| `force_field/Na+.itp`     | Molecular topology file for Na+. |
| `mdp/mdout.mdp`           | GROMACS molecular dynamics parameter file used for the NVT production simulations. |
| `systems/`                | Initial configurations and topology files for all electrolyte compositions investigated in this study. |
| `systems/*/confout_*.gro` | Initial configuration files for the five independent NVT production simulations for each electrolyte system. |
| `systems/*/topol.top`     | GROMACS topology files defining the molecular composition and force-field inclusion for each electrolyte system. |
| `systems/*/nonbond.itp`   | Nonbonded interaction parameters for each electrolyte system. |
| `README.md`               | Description of the repository, simulation details, file organization, and reproduction instructions. |

------------------------------------------------------------------------

## Reproduction of NVT Production Simulations

A typical NVT production simulation can be prepared using the following 
GROMACS command:

```bash
gmx grompp \
-f mdout.mdp \
-c confout_*.gro \
-p topol.top \
-o md.tpr
```

The production simulation can then be performed using:

```bash
gmx mdrun -s md.tpr
```

Before running the simulations, ensure that all required force-field files are
located in the appropriate directories and correctly referenced in the topology
file (`systems/*/topol.top`).

------------------------------------------------------------------------

## Data Availability

The molecular dynamics simulation input files used in this study, including
force-field parameters, GROMACS simulation parameters, topology files, and
initial configurations, are openly available in this repository.

------------------------------------------------------------------------

## Citation

If you use the simulation input files provided in this repository, please cite the
following publication:

Authors:
Hongjin Li, Tao Wang, Shu Li, Tianying Yan

Title:
The Effects of Strongly and Weakly Solvating Electrolytes on Ionic Conductivity in Sodium-Ion Battery Electrolytes

Journal:

Year:

DOI:



