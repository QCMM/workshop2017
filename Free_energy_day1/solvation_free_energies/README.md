# Solvation free energies in implicit and explicit solvent with Yank

This directory provides `run_hydration.py`, a simple command-line script which runs Yank.
Basically it provides a wrapper which helps create Yank YAML input for some common use cases, allowing hydration free energy calculations:
- in implicit solvent (GBSA)
- in explicit solvent (TIP3P, but easily generalizable to TIP4PEw)
- From mol2, sdf, or pdb files
- From SMILES or IUPAC names

For phenol, for example, in GBSA solvent, I get a hydration free energy of -10.077 +- 0.008 kT over 5000 iterations.
Values for 500 iterations in implicit solvent are quite consistent; I obtain -10.038 +- 0.026 kT, so very similar.
Implicit solvent converges particularly rapidly for small rigid solutes, since there is very little to sample.
For molecules with rotatable bonds, many more iterations may be required, even in implicit solvent.

See `python run_hydration.py` for usage information

## Manifest
- [`run_hydration.py`](run_hydration.py): Hydration free energy calculation script which just drives Yank hydration free energy calculations
