# Software prerequisites for these tutorials

This material draws heavily from a ["getting started"](https://github.com/MobleyLab/drug-computing/blob/master/uci-pharmsci/getting-started.md) document I prepared for a class, as well as the prerequisites provided in this host-guest Jupyter notebook which will be adapted for use here.

**Potential bottleneck**: This content requires a (free for academics) OpenEye license, which can take some time to obtain after filling out a license request form.

## Ensure you have a working installation of anaconda python (or miniconda).

Begin by ensuring you either install `miniconda` or obtain the full Anaconda python and associated conda package manager.
We recommend just installing Anaconda python:

Download the Anaconda installation file or Download it from the website or use (from the command prompt)

> `wget https://repo.continuum.io/archive/Anaconda3-4.4.0-Linux-x86_64.sh`

Install Anaconda (this may take 15-30mins):

> `bash Anaconda3-4.4.0-Linux-x86_64.sh -b`

Make sure the anaconda3 path is added to your `~/.bash_profile` (often this is automatically added by the installer, but make sure it ends up there), e.g. via:

> `echo export PATH="$HOME/anaconda3/bin:$PATH" >> ~/.bash_profile`

When it asks you to add Anaconda to your bash shell PATH, select YES.

Check that Anaconda installed properly by running the command `python`. Its output should look something like:

```
Python 3.6.0 |Anaconda 4.3.0 (64-bit)| (default, Dec 23 2016, 12:22:00)
[GCC 4.4.7 20120313 (Red Hat 4.4.7-1)] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

## Many additional prerequisites can be conda-installed:

```
# Install the gcc and gfortran compilers
conda install gcc libgfortran

# Install OpenMM, openforcefield, yank, parmed, and openmoltools
conda install -c omnia openmm==7.1.0rc1 openforcefield parmed yank openmoltools pdbfixer solvationtoolkit
# Install oeommtools for interfacing OpenEye and OpenMM
conda install -c OpenEye/label/Orion -c omnia oeommtools
# Install some other useful libraries
conda install -c conda-forge nb_conda mpld3 scikit-learn seaborn nglview
```

For `nglview` viewing of 3D structures within a Jupyter notebook, you will likely also need to run (from the command-line) `jupyter nbextension install --py nglview-js-widgets --user` and `jupyter-nbextension enable nglview --py --sys-prefix`.


## Additional materials can be installed via pip, such as the OpenEye toolkits

Take your OpenEye license file, `oe_license.txt`, and put it somewhere safe, then add its location to your environment, then pip install the OpenEye Python toolkits and `oenotebook`
```
#Add the OE_LICENSE to your ~/.bash_profile
# (Here, replace <PATHTOFILE> with the path of the place you have put this file)
echo export OE_LICENSE="<PATHTOFILE>/oe_license.txt" >> ~/.bash_profile

#Install the OpenEye package and toolkits and the oenotebook Jupyter helper
pip install -i https://pypi.anaconda.org/OpenEye/simple OpenEye-toolkits
pip install --pre --extra-index-url https://pypi.anaconda.org/OpenEye/channel/beta/simple OpenEye-oenotebook
```

Verify the installation with the command `oecheminfo.py`.
The output should look something like:
```
Installed OEChem version: 2.1.1 platform: linux-g++4.x-x64 built: 20170210

Examples: /home/limn1/anaconda3/envs/drugcomp/lib/python3.5/site-packages/openeye/examples
Doc Examples: /home/limn1/anaconda3/envs/drugcomp/lib/python3.5/site-packages/openeye/docexamples

code| ext           | description                      |read? |write?
----+---------------+----------------------------------+------+------
  1 | smi           | Canonical stereo SMILES          | yes  | yes
  2 | mdl,mol,rxn   | MDL Mol                          | yes  | yes
  3 | pdb,ent       | PDB                              | yes  | yes
  4 | mol2,syb      | Tripos MOL2                      | yes  | yes
  5 | usm           | Non-Canonical non-stereo SMILES  | yes  | yes
  6 | ism,isosmi    | Canonical stereo SMILES          | yes  | yes
  7 | mol2h         | MOL2 with H                      | yes  | yes
  8 | sdf,sd        | MDL SDF                          | yes  | yes
  9 | can           | Canonical non-stereo SMILES      | yes  | yes
 10 | mf            | Molecular Formula                | no   | yes
 11 | xyz           | XYZ                              | yes  | yes
 12 | fasta,seq     | FASTA                            | yes  | yes
 13 | mopac,pac     | MOPAC                            | no   | yes
 14 | oeb           | OEBinary v2                      | yes  | yes
 15 | dat,mmd,mmod  | Macromodel                       | yes  | yes
 16 | sln           | Tripos SLN                       | no   | yes
 17 | rdf,rd        | MDL RDF                          | yes  | no
 18 | cdx           | ChemDraw CDX                     | yes  | yes
 19 | skc           | MDL ISIS Sketch File             | yes  | no
 20 | inchi         | IUPAC InChI                      | no   | yes
 21 | inchikey      | IUPAC InChI Key                  | no   | yes
 22 | csv           | Comma Separated Values           | yes  | yes
 23 | json          | JavaScript Object Notation       | yes  | yes
----+---------------+----------------------------------+------+------
```

You should doublecheck that the OpenEye installation is working corectly by opening python (on the command prompt) or a Jupyter notebook and typing:
```python
from openeye.oechem import *
mol = OEMol()
```
and you should get no errors.

## Interactive Jupyter notebook presentations

Some of the content in this course may use presentations done from Jupyter notebooks that allow running Python code from the presentation itself. These are done via Damian Vila's RISE module, which is installed via:
`conda install -c damianavila82 rise`
then `jupyter-nbextension install rise --py --sys-prefix` and `jupyter-nbextension enable rise --py --sys-prefix`
