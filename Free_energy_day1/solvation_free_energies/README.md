# Solvation free energies in implicit and explicit solvent with Yank

This directory provides `run_hydration.py`, a simple command-line script which runs Yank.
Basically it provides a wrapper which helps create Yank YAML input for some common use cases, allowing hydration free energy calculations:
- in implicit solvent (GBSA)
- in explicit solvent (TIP3P, but easily generalizable to TIP4PEw)
- From mol2, sdf, or pdb files
- From SMILES or IUPAC names

See `python run_hydration.py` for usage information

## Manifest
- [`run_hydration.py`](run_hydration.py): Hydration free energy calculation script which just drives Yank hydration free energy calculations
