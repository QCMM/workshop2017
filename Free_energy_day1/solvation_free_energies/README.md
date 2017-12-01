# Solvation free energies in implicit and explicit solvent with Yank

This directory provides Session 1's material on solvation free energy calculations; the key content is in the Jupyter notebook [`Session1.ipynb`](Session1.ipynb) which can be launched from the command-line by `jupyter notebook Session1.ipynb`.

This also draws on `run_hydration.py`, a simple command-line script which runs Yank.
Basically this script provides a wrapper which helps create Yank YAML input for some common use cases, allowing hydration free energy calculations:
- in implicit solvent (GBSA)
- in explicit solvent (TIP3P, but easily generalizable to TIP4PEw)
- From mol2, sdf, or pdb files
- From SMILES or IUPAC names

For phenol, for example, in GBSA solvent, I get a hydration free energy of -10.077 +- 0.008 kT over 5000 iterations.
Values for 500 iterations in implicit solvent are quite consistent; I obtain -10.038 +- 0.026 kT, so very similar.
Implicit solvent converges particularly rapidly for small rigid solutes, since there is very little to sample.
For molecules with rotatable bonds, many more iterations may be required, even in implicit solvent.
I did also run an explicit solvent calculation for phenol (from name) for 1000 iterations and obtained a value of -5.647 +- 0.147 kcal/mol. Experiment: -6.60+/-0.20 kcal/mol; previously calculated (FreeSolv) -5.71+/-0.03 kcal/mol.

See `python run_hydration.py` for usage information

## Manifest

### Things you may want to use
- [`run_hydration.py`](run_hydration.py): Hydration free energy calculation script which just drives Yank hydration free energy calculations
- [`Session1.ipynb`](Session1.ipynb): Jupyter notebook with Session 1's contents/examples.

### Supporting materials
- [`images`](images): Images used by files here, especially Jupyter notebooks.
- [`sample_files`](sample_files): Other files, such as molecule inputs, used by Jupyter notebooks here; also a sample explicit solvent hydration free energy calculation.
