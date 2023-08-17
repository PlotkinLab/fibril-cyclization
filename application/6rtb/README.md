# Application to completing fibril structures

![alt text](https://github.com/PlotkinLab/fibril-cyclization/blob/main/application/6rtb/application.png?raw=true)

The RosettaScripts script presented here can also be used to complete fibril structures that are missing segments of amino acid sequence. The flexible region in fibril structures is often not resolved due to its flexibility. The workflow in designing linkers can also be used to patch these missing regions and provide complete contiguous structures. These complete structures could serve as initial conformations for downstream simulations (which require complete structures). 

We applied our Rosetta procedure to an alpha-synuclein fibril polymorph 2b structure (PDB code: 6RTB, chain G-K), which has two gaps in primary sequence, 25-34 and 57-61. The script was modified to assign linker sequences directly from the alpha-synuclein primary sequence
