# Free Energy Calculations Tutorial

This provides tutorial/example material relating to performing free energy calculations with OpenMM and Yank, as well as some introductory materials/examples relating to OpenMM.
This content was prepared for the Symposium on Molecular Interactions in Chemistry and Biology 2017, of December, 2017, and in particular Day 1 of the Workshop, focusing on free energy calculations.

## Basic outline of the day

### Morning lecture/theory session:
- Force fields (Vohringer-Martinez; about 1 hr 15 min)
- Break
- Free energy calculations (Mobley; about 1 hr 15 min)

### Afternoon hands-on/tutorial session:
- **Basic hydration free energy calculations with Yank/OpenMM** ([`solvation_free_energies/Session1.ipynb`](solvation_free_energies/Session1.ipynb), 1.5 hours)
  - Pick your favorite (small) molecule and start an implicit solvent hydration free energy calculation using prepared code, with Yank (using OpenMM). Do this using [`solvation_free_energies/run_hydration.py`](solvation_free_energies/run_hydration.py); see `python solvation_free_energies.py -h` and the README in that directory for further instructions.
  - Discuss how to prepare molecules more generally (Jupyter notebook [`solvation_free_energies/Session1.ipynb`](solvation_free_energies/Session1.ipynb))
  - Look at what Yank is doing, briefly discuss why
  - Analyze a sample explicit solvent hydration calculation
  - Discuss analysis/mixing
- **Break (15 min)**
- **Analysis and a view of what's going on under the hood/using OpenMM (1 hour)**
    - Analyze implicit solvent hydration calculation run earlier (if not already done)
    - Session 2 Jupyter notebook ([`OpenMM/Session2.ipynb`](OpenMM/Session2.ipynb)) covering:
        - Some OpenMM basics
        - Example of a solution density calculation (GAFF force field) which stops when converged
        - Analysis of density calculation
        - Setup of density calculation with alternate force field

- **Break (15 min)**
- **A binding example: Host-guest docking and free energy setup with visualization (1 hour)**
    - Jupyter notebook with guest structure preparation, host-guest docking, visualization, running a short OpenMM simulation
    - Preparation of inputs for binding calculations for Yank -- example provided; may not be time to work through it
    - Sample host-guest binding data and analysis provided (may or may not have time to work through it; determined based on interest and time)

## Manifest
- [`prerequisites.md`](prerequisites.md): The software you need for these tutorials should already be available on the computers you will use for this workshop. However, this document lists what you would need to install and how if you would like to use these tools on your own resources later.
- [`solvation_free_energies`](solvation_free_energies): Content relating to calculation of solvation free energies.
- [`OpenMM`](OpenMM): Content relating to OpenMM-centric sessions (Session 2 and 3).

## Authors
- David L. Mobley (UC Irvine)
- Esteban Vohringer-Martinez (University of Concepción)

## Acknowledgments
Various pieces of code/examples here are drawn from other individuals and other sources; credit is typically given where this is done (e.g. in the code itself).
In addition, we particularly thank:
- Maximilano R. Troncoso for help with software prerequisites/installation and testing
- Léa El Khoury for host-guest examples and explicit solvent hydration free energy outputs
