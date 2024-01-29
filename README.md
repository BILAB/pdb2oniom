# pdb2oniom

A python implementation of pdb2oniom for QM/MM (ONIOM) calculations.

An alternative of `pdb2oniom` perl script originally developed at [TAO package](http://schlegelgroup.wayne.edu/Software/oniomtoolTAO/TAOtutorial.html). The feature to import force field parameters from an input parm7 file is inspired by the [CATs package](https://github.com/kulhanek/cats) and its `topcrd2mmcom` command.

## Feature

- Generate a Gaussian input file for ONIOM calculations from AMBER topology (`.parm7`) and restart (`.rst7`) files.
- The force field parameters in the AMBER topology file will be written in the output gjf file automatically.

## Usage

Requirement: [NumPy](https://www.numpy.org), [SciPy](https://scipy.org/), and [ParmEd](https://github.com/ParmEd/ParmEd). You don't need to install ParmEd if you have already installed [AmberTools](https://ambermd.org/AmberTools.php) on your machine.

```bash
python3 -m pip install absl-py numpy scipy ParmEd
```

An example to run:

```bash
$ python3 pdb2oniom.py -p init.parm7 -r init.rst7 --resid corelist.txt -o oniominput1.gjf

I1226 01:27:50.008807 pdb2oniom.py:341] pdb2oniom.py ver.0.2; Amber parm and rst7 files to Gaussian ONIOM input file.
I1226 01:27:50.410809 pdb2oniom.py:345] Total charge of low layer is calculated -7
I1226 01:27:50.410898 pdb2oniom.py:346] Core residues list file corelist.txt provided.
I1226 01:27:50.410926 pdb2oniom.py:347] All residues within 999.0 Å from core region are free to move (0) during geometry optimization.
I1226 01:27:50.461310 pdb2oniom.py:137] 12983 atoms are set to be movable during geometry optimization.
I1226 01:27:50.923890 pdb2oniom.py:359] Opening file oniominput1.gjf for output ...
I1226 01:27:50.924405 pdb2oniom.py:362] Successfully wrote oniominput1.gjf file.
I1226 01:27:50.924434 pdb2oniom.py:363] Opening file oniominput1.gjf.onb for output ...
I1226 01:27:50.924645 pdb2oniom.py:367] Successfully wrote oniominput1.gjf.onb file.
I1226 01:27:50.924666 pdb2oniom.py:368] pdb2oniom.py ends.
```
