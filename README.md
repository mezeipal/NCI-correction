# NCI-correction
Universal non-covalent interaction correction to DFT from machine learning

Install the QML code:
http://www.qmlcode.org/installation.html

Modify the dft-nci.py file:

Required modifications:

Select a baseline method by defining the variable "method = N", where N can be
0: Direct ML
1: BLYP-NCI
2: PBE-NCI
3: TPSS-NCI
4: SCAN-NCI
5: B3LYP-NCI
6: PBE0-NCI

Specify the folders containing the xyz files of the test systems as
"X_test = rep_mol("test/folder", X_test)" for molecular systems
"X_test = rep_sol("test/folder", X_test)" for periodic solids

Optional modifications:

Include more training folders with the energy (txt) and geometries (xyz) files as
"X_training = rep_mol("training/folder", X_training)" for molecular systems
"X_training = rep_sol("training/folder", X_training)" for periodic solids

Alter the list of kernel widths (sigmas), or the regularization strength (lmda) as
"sigmas = [2.0**8]"
"lmda = 1e-8"

Include more atoms in the dictionary, or increase the size of the representation as
"choices = {'H': 1, 'C': 6, 'N': 7, 'O': 8, 'F': 9, 'Cl': 17, 'Br': 35, 'I': 53}"
"max_size=155", "neighbors=429"

Run the code:
python dft-nci.py
