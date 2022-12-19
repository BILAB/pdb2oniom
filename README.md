# pdb2oniom
A python implementation of pdb2oniom for QM/MM (ONIOM) calculations.

An alternative version of `pdb2oniom` perl script originally developed at [TAO package](http://schlegelgroup.wayne.edu/Software/oniomtoolTAO/TAOtutorial.html) and the feature is also inspired by [CATS package](https://github.com/kulhanek/cats) and its `topcrd2mmcom`.

## Feature

- Generate a Gaussian input file for ONIOM calculations from AMBER topology (`.parm7`) and restart (`.rst7`) files.
- The bond information and parameters in the AMBER topology file will be written in the output gjf file.

## Usage

Requirement: [Abseil](https://github.com/abseil/abseil-py), [NumPy](https://www.numpy.org), [SciPy](https://scipy.org/), and [ParmEd](https://github.com/ParmEd/ParmEd). You don't need to install ParmEd if you have already installed [AmberTools](https://ambermd.org/AmberTools.php) on your machine.

```bash
$ python3 -m pip install absl-py numpy scipy ParmEd
```

An example to run:

```bash
$ python3 /path/to/pdb2oniom.py -p init.parm7 -r init.rst7 --resid corelist_sample.txt -o out.gjf
I1219 16:49:46.431103 140704715987136 pdb2oniom.py:338] pdb2oniom.py ver.0.1; Amber parm and rst7 files to Gaussian ONIOM input file.
I1219 16:49:46.928725 140704715987136 pdb2oniom.py:342] Total charge of low layer is calculated -7
I1219 16:49:46.928815 140704715987136 pdb2oniom.py:343] Core residues list file corelist_sample.txt provided.
I1219 16:49:46.928857 140704715987136 pdb2oniom.py:344] All residues within 7.0 Å from core region are free to move (0) during geometry optimization.
I1219 16:49:47.005849 140704715987136 pdb2oniom.py:137] 3064 atoms are set to be movable during geometry optimization.
I1219 16:49:47.820617 140704715987136 pdb2oniom.py:355] Opening file out.gjf for output ...
I1219 16:49:47.821306 140704715987136 pdb2oniom.py:358] Successfully wrote out.gjf file.
I1219 16:49:47.821386 140704715987136 pdb2oniom.py:359] pdb2oniom.py ends.
```