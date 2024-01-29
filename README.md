# pdb2oniom

A python implementation of pdb2oniom for QM/MM (ONIOM) calculations.

An alternative of `pdb2oniom` perl script originally developed at [TAO package](http://schlegelgroup.wayne.edu/Software/oniomtoolTAO/TAOtutorial.html). The feature to import force field parameters from an input parm7 file is inspired by the [CATs package](https://github.com/kulhanek/cats) and its `topcrd2mmcom` command.

## Feature

- Generate a Gaussian input file for ONIOM calculations from AMBER topology (`.parm7`) and restart (`.rst7`) files.
- The force field parameters in the AMBER topology file will be written in the output gjf file automatically.

## Installation

```bash
# install from GitHub
python3.11 -m pip install git+https://github.com/BILAB/pdb2oniom.git
# upgrade
python3.11 -m pip uninstall pdb2oniom -y && python3.11 -m pip install --upgrade git+https://github.com/BILAB/pdb2oniom.git
```

## Usage

An example to run:

```bash
$ pdb2oniom_py -p leap.parm7 -r leap.rst7 --resid corelist.txt -n 7

2024-01-29 15:34:52,406 pdb2oniom.py:782 - INFO - pdb2oniom.py ver.0.3.2: Amber parm and rst7 files to Gaussian ONIOM input file.
2024-01-29 15:34:53,456 pdb2oniom.py:691 - INFO - Total charge of low layer is calculated -18
2024-01-29 15:34:53,456 pdb2oniom.py:692 - INFO - Core residues list file corelist.txt provided.
2024-01-29 15:34:53,456 pdb2oniom.py:693 - INFO - All residues within 7.0 Å from core region are free to move (0) during geometry optimization.
2024-01-29 15:34:53,523 pdb2oniom.py:146 - INFO - 2289 atoms are set to be movable during geometry optimization.
2024-01-29 15:34:54,790 pdb2oniom.py:705 - INFO - Opening file newinput.gjf for output ...
2024-01-29 15:34:54,795 pdb2oniom.py:708 - INFO - Successfully wrote newinput.gjf file.
2024-01-29 15:34:54,795 pdb2oniom.py:709 - INFO - Opening file newinput.gjf.onb for output ...
2024-01-29 15:34:54,799 pdb2oniom.py:713 - INFO - Successfully wrote newinput.gjf.onb file.
2024-01-29 15:34:54,799 pdb2oniom.py:714 - INFO - pdb2oniom.py ends.

2024-01-29 15:34:54,799 pdb2oniom.py:715 - INFO - NOTE: The charges and multiplicity of high layer should be modified for your calculations. Please use GaussView 6 to modify the QM regions and link atoms.
```
