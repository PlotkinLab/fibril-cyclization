# fibril-cyclization

**About**

This repository contains RosettaScript scripts to cyclize the protein fibrils.

![alt text](https://github.com/PlotkinLab/fibril-cyclization/blob/main/workflow.png?raw=true)

The following movers were applied in sequence during the procedure.

First, we used PeptideStubMover to add glycines on the side-most peptide chain. Then, we used PeptideCyclizeMover and DeclareBond mover to set up the energy function for a head-to-tail peptide bond on the side-most peptide chain. Finally, we used the GeneralizedKIC mover to sample various linker conformations that cyclize the side-most peptide without clashes.

To graft the linker structure from the side-most chain to the rest of the chains, we applied a series of CCDEndsGraftMover. Before applying the FastRelax mover, we used the AtomTree mover to ensure that the relaxation of the linker would not affect the rest of the structure. Namely, the linker residues are at the end of the AtomTree. We also used the SetupNCS mover to restrain the same backbone torsional angle across chains.

Sequence design was performed using the FastDesign mover with resfile restraints, where negative $\phi$ was restricted to becoming L-amino acids, and positive $\phi$ was restricted to becoming D-amino acids during design. Before FastDesign, we applied the SetupForSequenceSymmetryMover to enforce identical linker sequences across all chains.


**How to run the scipt?**

`./run.sh`

Before running the script, edit the `$ROSETTA3` to be your Rosetta installed path


**Output**

`score.sc` file contains the values of the energy function components and user-defined filter values.

`out.silent` file contains the compressed format of the designed structures

## Reference

The development of fibril-cyclization scripts is funded by academic research grants. To help us fund development, we humbly ask that you cite the following papers:

(To be submitted)
