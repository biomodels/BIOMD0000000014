# BIOMD0000000014: MAPK_in_Scaffold

## Installation

Download this repository, and install with distutils

`python setup.py install`

Or, install using pip

`pip install git+https://github.com/biomodels/BIOMD0000000014.git`

To install a specific version (in this example, from the 2014-09-16 BioModels release)

`pip install git+https://github.com/biomodels/BIOMD0000000014.git@20140916`

## Usage

Importing the model package.

`import BIOMD0000000014 as model`

Get the SBML string from the model

`print model.sbmlString`

If [python-libsbml](https://pypi.python.org/pypi/python-libsbml) bindings are
installed, the libsbml.SBMLDocument object is also accessible

`model.sbml`


# Model Notes


# MAPK cascade on a scaffold

Citation  
---  
Levchenko, A., Bruck, J., Sternberg, P.W. (2000) .Scaffold proteins may
biphasically affect the levels of mitogen-activated protein kinase signaling
and reduce its threshold properties. Proc. Natl. Acad. Sci. USA
97(11):5818-5823. [ http://www.pnas.org/cgi/content/abstract/97/11/5818
](http://www.pnas.org/cgi/content/abstract/97/11/5818)  
Description  
---  
This model describes a basic 3-stage Mitogen Activated Protein Kinase (MAPK).
Kinases in solution are written as K[3,J], K[2,J], K[1,J] for MAPKKK, MAPKK,
and MAPK, respectively, J indicates the phosphorylation level, J=0,1 for K3
and J=0,1,2 for K2 and K1. Scaffolds have three slots, for MAPK, MAPKK, and
MAPKKK, respectively. Bound and free scaffold are denoted as S[i,j,k], where
i, j, and k indicate the binding of K[1,i], K[2,j] and K[3,k] in their
respective slots. Here i,j=-1,0,1,or,2 and k=-1,0,or,1. A value of -1 means
the slot is empty, 0 means the unphorphorylated kinase is bound, 1 means the
singly phosphorylated kinase is bound, and 2 means the doubly phosphorylated
kinase is bound. Thus S[1,-1,2] is a scaffold with K[3,1] bound in the first
slot and K[1,2] in the third slot, while the second slot is empty.Note:
Indices X[I,J,K] are translated into the unindexed variable X_I_J_K and so
forth in the SBML. Negative indices are translated as mI, etc, thus S[1,-1,2]
becomes S_1_m1_2.  
Rate constant       | Reaction  
---|---  
a10 = 5. | MAPKP + K[1, 2] -> K_MAPKP[1, 2]  
a1 = 1. | RAFK + K[3, 0] -> K_RAFK[3, 0]  
a2 = 0.5 | RAFP + K[3, 1] -> K_RAFP[3, 1]  
a3 = 3.3 | K[2, 0] + K[3, 1] -> K_K[2, 0, 3,  1]  
a4 = 10. | MEKP + K[2, 1] -> K_MEKP[2, 1]  
a5 = 3.3 | K[2, 1] + K[3, 1] -> K_K[2, 1, 3,  1]  
a6 = 10. | MEKP + K[2, 2] -> K_MEKP[2, 2]  
a7 = 20. | K[1, 0] + K[2, 2] -> K_K[1, 0, 2,  2]  
a8 = 5. | MAPKP + K[1, 1] -> K_MAPKP[1, 1]  
a9 = 20. | K[1, 1] + K[2, 2] -> K_K[1, 1, 2,  2]  
d10 = 0.4 | K_MAPKP[1, 2] -> MAPKP + K[1, 2]  
d1 = 0.4 | K_RAFK[3, 0] -> RAFK + K[3, 0]  
d1a = 0 | S_RAFK[0, 0, 0] -> RAFK + S[0, 0, 0]  
d1a = 0 | S_RAFK[0, -1, 0] -> RAFK + S[0, -1,  0]  
d1a = 0 | S_RAFK[0, 1, 0] -> RAFK + S[0, 1, 0]  
d1a = 0 | S_RAFK[0, 2, 0] -> RAFK + S[0, 2, 0]  
d1a = 0 | S_RAFK[-1, 0, 0] -> RAFK + S[-1, 0,  0]  
d1a = 0 | S_RAFK[1, 0, 0] -> RAFK + S[1, 0, 0]  
d1a = 0 | S_RAFK[-1, -1, 0] -> RAFK + S[-1, -1,  0]  
d1a = 0 | S_RAFK[-1, 1, 0] -> RAFK + S[-1, 1,  0]  
d1a = 0 | S_RAFK[1, -1, 0] -> RAFK + S[1, -1,  0]  
d1a = 0 | S_RAFK[1, 1, 0] -> RAFK + S[1, 1, 0]  
d1a = 0 | S_RAFK[-1, 2, 0] -> RAFK + S[-1, 2,  0]  
d1a = 0 | S_RAFK[1, 2, 0] -> RAFK + S[1, 2, 0]  
d1a = 0 | S_RAFK[2, 0, 0] -> RAFK + S[2, 0, 0]  
d1a = 0 | S_RAFK[2, -1, 0] -> RAFK + S[2, -1,  0]  
d1a = 0 | S_RAFK[2, 1, 0] -> RAFK + S[2, 1, 0]  
d1a = 0 | S_RAFK[2, 2, 0] -> RAFK + S[2, 2, 0]  
d2 = 0.5 | K_RAFP[3, 1] -> RAFP + K[3, 1]  
d3 = 0.42 | K_K[2, 0, 3, 1] -> K[2, 0] + K[3,  1]  
d4 = 0.8 | K_MEKP[2, 1] -> MEKP + K[2, 1]  
d5 = 0.4 | K_K[2, 1, 3, 1] -> K[2, 1] + K[3,  1]  
d6 = 0.8 | K_MEKP[2, 2] -> MEKP + K[2, 2]  
d7 = 0.6 | K_K[1, 0, 2, 2] -> K[1, 0] + K[2,  2]  
d8 = 0.4 | K_MAPKP[1, 1] -> MAPKP + K[1, 1]  
d9 = 0.6 | K_K[1, 1, 2, 2] -> K[1, 1] + K[2,  2]  
k10 = 0.1 | K_MAPKP[1, 2] -> MAPKP + K[1, 1]  
k1 = 0.1 | K_RAFK[3, 0] -> RAFK + K[3, 1]  
k1 = 0.1 | S_RAFK[0, 0, 0] -> RAFK + S[0, 0, 1]  
k1 = 0.1 | S_RAFK[0, -1, 0] -> RAFK + S[0, -1,  1]  
k1 = 0.1 | S_RAFK[0, 1, 0] -> RAFK + S[0, 1, 1]  
k1 = 0.1 | S_RAFK[0, 2, 0] -> RAFK + S[0, 2, 1]  
k1 = 0.1 | S_RAFK[-1, 0, 0] -> RAFK + S[-1, 0,  1]  
k1 = 0.1 | S_RAFK[1, 0, 0] -> RAFK + S[1, 0, 1]  
k1 = 0.1 | S_RAFK[-1, -1, 0] -> RAFK + S[-1, -1,  1]  
k1 = 0.1 | S_RAFK[-1, 1, 0] -> RAFK + S[-1, 1,  1]  
k1 = 0.1 | S_RAFK[1, -1, 0] -> RAFK + S[1, -1,  1]  
k1 = 0.1 | S_RAFK[1, 1, 0] -> RAFK + S[1, 1, 1]  
k1 = 0.1 | S_RAFK[-1, 2, 0] -> RAFK + S[-1, 2,  1]  
k1 = 0.1 | S_RAFK[1, 2, 0] -> RAFK + S[1, 2, 1]  
k1 = 0.1 | S_RAFK[2, 0, 0] -> RAFK + S[2, 0, 1]  
k1 = 0.1 | S_RAFK[2, -1, 0] -> RAFK + S[2, -1,  1]  
k1 = 0.1 | S_RAFK[2, 1, 0] -> RAFK + S[2, 1, 1]  
k1 = 0.1 | S_RAFK[2, 2, 0] -> RAFK + S[2, 2, 1]  
k1a = 100 | RAFK + S[0, 0, 0] -> S_RAFK[0, 0, 0]  
k1a = 100 | RAFK + S[0, -1, 0] -> S_RAFK[0, -1,  0]  
k1a = 100 | RAFK + S[0, 1, 0] -> S_RAFK[0, 1, 0]  
k1a = 100 | RAFK + S[0, 2, 0] -> S_RAFK[0, 2, 0]  
k1a = 100 | RAFK + S[-1, 0, 0] -> S_RAFK[-1, 0,  0]  
k1a = 100 | RAFK + S[1, 0, 0] -> S_RAFK[1, 0, 0]  
k1a = 100 | RAFK + S[-1, -1, 0] -> S_RAFK[-1, -1,  0]  
k1a = 100 | RAFK + S[-1, 1, 0] -> S_RAFK[-1, 1,  0]  
k1a = 100 | RAFK + S[1, -1, 0] -> S_RAFK[1, -1,  0]  
k1a = 100 | RAFK + S[1, 1, 0] -> S_RAFK[1, 1, 0]  
k1a = 100 | RAFK + S[-1, 2, 0] -> S_RAFK[-1, 2,  0]  
k1a = 100 | RAFK + S[1, 2, 0] -> S_RAFK[1, 2, 0]  
k1a = 100 | RAFK + S[2, 0, 0] -> S_RAFK[2, 0, 0]  
k1a = 100 | RAFK + S[2, -1, 0] -> S_RAFK[2, -1,  0]  
k1a = 100 | RAFK + S[2, 1, 0] -> S_RAFK[2, 1, 0]  
k1a = 100 | RAFK + S[2, 2, 0] -> S_RAFK[2, 2, 0]  
k2 = 0.1 | K_RAFP[3, 1] -> RAFP + K[3, 0]  
k3 = 0.1 | K_K[2, 0, 3, 1] -> K[2, 1] + K[3,  1]  
k3 = 0.1 | S[0, 0, 1] -> S[0, 1, 1]  
k3 = 0.1 | S[-1, 0, 1] -> S[-1, 1, 1]  
k3 = 0.1 | S[1, 0, 1] -> S[1, 1, 1]  
k3 = 0.1 | S[2, 0, 1] -> S[2, 1, 1]  
k4 = 0.1 | K_MEKP[2, 1] -> MEKP + K[2, 0]  
k5 = 0.1 | K_K[2, 1, 3, 1] -> K[2, 2] + K[3,  1]  
k5a = 0.1 | S[0, 1, 1] -> S[0, 2, 1]  
k5a = 0.1 | S[-1, 1, 1] -> S[-1, 2, 1]  
k5a = 0.1 | S[1, 1, 1] -> S[1, 2, 1]  
k5a = 0.1 | S[2, 1, 1] -> S[2, 2, 1]  
k6 = 0.1 | K_MEKP[2, 2] -> MEKP + K[2, 1]  
k7 = 0.1 | K_K[1, 0, 2, 2] -> K[1, 1] + K[2,  2]  
k7 = 0.1 | S[0, 2, 0] -> S[1, 2, 0]  
k7 = 0.1 | S[0, 2, -1] -> S[1, 2, -1]  
k7 = 0.1 | S[0, 2, 1] -> S[1, 2, 1]  
k8 = 0.1 | K_MAPKP[1, 1] -> MAPKP + K[1, 0]  
k9 = 0.1 | K_K[1, 1, 2, 2] -> K[1, 2] + K[2,  2]  
k9a = 0.1 | S[1, 2, 0] -> S[2, 2, 0]  
k9a = 0.1 | S[1, 2, -1] -> S[2, 2, -1]  
k9a = 0.1 | S[1, 2, 1] -> S[2, 2, 1]  
koff = 0.5 | S[0, 0, 0] -> K[1, 0] + S[-1, 0,  0]  
koff = 0.5 | S[0, 0, 0] -> K[2, 0] + S[0, -1,  0]  
koff = 0.5 | S[0, 0, 0] -> K[3, 0] + S[0, 0,  -1]  
koff = 0.5 | S[0, 0, -1] -> K[1, 0] + S[-1, 0,  -1]  
koff = 0.5 | S[0, 0, 1] -> K[1, 0] + S[-1, 0,  1]  
koff = 0.5 | S[0, 0, -1] -> K[2, 0] + S[0, -1,  -1]  
koff = 0.5 | S[0, 0, 1] -> K[2, 0] + S[0, -1,  1]  
koff = 0.5 | S[0, -1, 0] -> K[1, 0] + S[-1, -1,  0]  
koff = 0.5 | S[0, 1, 0] -> K[1, 0] + S[-1, 1,  0]  
koff = 0.5 | S[0, -1, 0] -> K[3, 0] + S[0, -1,  -1]  
koff = 0.5 | S[0, 1, 0] -> K[3, 0] + S[0, 1,  -1]  
koff = 0.5 | S[0, -1, -1] -> K[1, 0] + S[-1, -1,  -1]  
koff = 0.5 | S[0, -1, 1] -> K[1, 0] + S[-1, -1,  1]  
koff = 0.5 | S[0, 1, -1] -> K[1, 0] + S[-1, 1,  -1]  
koff = 0.5 | S[0, 1, 1] -> K[1, 0] + S[-1, 1,  1]  
koff = 0.5 | S[0, 2, 0] -> K[1, 0] + S[-1, 2,  0]  
koff = 0.5 | S[0, 2, 0] -> K[3, 0] + S[0, 2,  -1]  
koff = 0.5 | S[0, 2, -1] -> K[1, 0] + S[-1, 2,  -1]  
koff = 0.5 | S[0, 2, 1] -> K[1, 0] + S[-1, 2,  1]  
koff = 0.5 | S[-1, 0, 0] -> K[2, 0] + S[-1, -1,  0]  
koff = 0.5 | S[1, 0, 0] -> K[2, 0] + S[1, -1,  0]  
koff = 0.5 | S[-1, 0, 0] -> K[3, 0] + S[-1, 0,  -1]  
koff = 0.5 | S[1, 0, 0] -> K[3, 0] + S[1, 0,  -1]  
koff = 0.5 | S[-1, 0, -1] -> K[2, 0] + S[-1, -1,  -1]  
koff = 0.5 | S[-1, 0, 1] -> K[2, 0] + S[-1, -1,  1]  
koff = 0.5 | S[1, 0, -1] -> K[2, 0] + S[1, -1,  -1]  
koff = 0.5 | S[1, 0, 1] -> K[2, 0] + S[1, -1,  1]  
koff = 0.5 | S[-1, -1, 0] -> K[3, 0] + S[-1, -1,  -1]  
koff = 0.5 | S[-1, 1, 0] -> K[3, 0] + S[-1, 1,  -1]  
koff = 0.5 | S[1, -1, 0] -> K[3, 0] + S[1, -1,  -1]  
koff = 0.5 | S[1, 1, 0] -> K[3, 0] + S[1, 1,  -1]  
koff = 0.5 | S[-1, 2, 0] -> K[3, 0] + S[-1, 2,  -1]  
koff = 0.5 | S[1, 2, 0] -> K[3, 0] + S[1, 2,  -1]  
koff = 0.5 | S[2, 0, 0] -> K[2, 0] + S[2, -1,  0]  
koff = 0.5 | S[2, 0, 0] -> K[3, 0] + S[2, 0,  -1]  
koff = 0.5 | S[2, 0, -1] -> K[2, 0] + S[2, -1,  -1]  
koff = 0.5 | S[2, 0, 1] -> K[2, 0] + S[2, -1,  1]  
koff = 0.5 | S[2, -1, 0] -> K[3, 0] + S[2, -1,  -1]  
koff = 0.5 | S[2, 1, 0] -> K[3, 0] + S[2, 1,  -1]  
koff = 0.5 | S[2, 2, 0] -> K[3, 0] + S[2, 2,  -1]  
kon = 10 | K[1, 0] + S[-1, 0, 0] -> S[0, 0,  0]  
kon = 10 | K[1, 0] + S[-1, 0, -1] -> S[0, 0,  -1]  
kon = 10 | K[1, 0] + S[-1, 0, 1] -> S[0, 0,  1]  
kon = 10 | K[1, 0] + S[-1, -1, 0] -> S[0, -1,  0]  
kon = 10 | K[1, 0] + S[-1, 1, 0] -> S[0, 1,  0]  
kon = 10 | K[1, 0] + S[-1, -1, -1] -> S[0, -1,  -1]  
kon = 10 | K[1, 0] + S[-1, -1, 1] -> S[0, -1,  1]  
kon = 10 | K[1, 0] + S[-1, 1, -1] -> S[0, 1,  -1]  
kon = 10 | K[1, 0] + S[-1, 1, 1] -> S[0, 1,  1]  
kon = 10 | K[1, 0] + S[-1, 2, 0] -> S[0, 2,  0]  
kon = 10 | K[1, 0] + S[-1, 2, -1] -> S[0, 2,  -1]  
kon = 10 | K[1, 0] + S[-1, 2, 1] -> S[0, 2,  1]  
kon = 10 | K[2, 0] + S[0, -1, 0] -> S[0, 0,  0]  
kon = 10 | K[2, 0] + S[0, -1, -1] -> S[0, 0,  -1]  
kon = 10 | K[2, 0] + S[0, -1, 1] -> S[0, 0,  1]  
kon = 10 | K[2, 0] + S[-1, -1, 0] -> S[-1, 0,  0]  
kon = 10 | K[2, 0] + S[1, -1, 0] -> S[1, 0,  0]  
kon = 10 | K[2, 0] + S[-1, -1, -1] -> S[-1, 0,  -1]  
kon = 10 | K[2, 0] + S[-1, -1, 1] -> S[-1, 0,  1]  
kon = 10 | K[2, 0] + S[1, -1, -1] -> S[1, 0,  -1]  
kon = 10 | K[2, 0] + S[1, -1, 1] -> S[1, 0,  1]  
kon = 10 | K[2, 0] + S[2, -1, 0] -> S[2, 0,  0]  
kon = 10 | K[2, 0] + S[2, -1, -1] -> S[2, 0,  -1]  
kon = 10 | K[2, 0] + S[2, -1, 1] -> S[2, 0,  1]  
kon = 10 | K[3, 0] + S[0, 0, -1] -> S[0, 0,  0]  
kon = 10 | K[3, 0] + S[0, -1, -1] -> S[0, -1,  0]  
kon = 10 | K[3, 0] + S[0, 1, -1] -> S[0, 1,  0]  
kon = 10 | K[3, 0] + S[0, 2, -1] -> S[0, 2,  0]  
kon = 10 | K[3, 0] + S[-1, 0, -1] -> S[-1, 0,  0]  
kon = 10 | K[3, 0] + S[1, 0, -1] -> S[1, 0,  0]  
kon = 10 | K[3, 0] + S[-1, -1, -1] -> S[-1, -1,  0]  
kon = 10 | K[3, 0] + S[-1, 1, -1] -> S[-1, 1,  0]  
kon = 10 | K[3, 0] + S[1, -1, -1] -> S[1, -1,  0]  
kon = 10 | K[3, 0] + S[1, 1, -1] -> S[1, 1,  0]  
kon = 10 | K[3, 0] + S[-1, 2, -1] -> S[-1, 2,  0]  
kon = 10 | K[3, 0] + S[1, 2, -1] -> S[1, 2,  0]  
kon = 10 | K[3, 0] + S[2, 0, -1] -> S[2, 0,  0]  
kon = 10 | K[3, 0] + S[2, -1, -1] -> S[2, -1,  0]  
kon = 10 | K[3, 0] + S[2, 1, -1] -> S[2, 1,  0]  
kon = 10 | K[3, 0] + S[2, 2, -1] -> S[2, 2,  0]  
kpoff = 0.05 | S[0, 0, 1] -> K[3, 1] + S[0, 0,  -1]  
kpoff = 0.05 | S[0, 1, 0] -> K[2, 1] + S[0, -1,  0]  
kpoff = 0.05 | S[0, 1, -1] -> K[2, 1] + S[0, -1,  -1]  
kpoff = 0.05 | S[0, 1, 1] -> K[2, 1] + S[0, -1,  1]  
kpoff = 0.05 | S[0, -1, 1] -> K[3, 1] + S[0, -1,  -1]  
kpoff = 0.05 | S[0, 1, 1] -> K[3, 1] + S[0, 1,  -1]  
kpoff = 0.05 | S[0, 2, 0] -> K[2, 2] + S[0, -1,  0]  
kpoff = 0.05 | S[0, 2, -1] -> K[2, 2] + S[0, -1,  -1]  
kpoff = 0.05 | S[0, 2, 1] -> K[2, 2] + S[0, -1,  1]  
kpoff = 0.05 | S[0, 2, 1] -> K[3, 1] + S[0, 2,  -1]  
kpoff = 0.05 | S[1, 0, 0] -> K[1, 1] + S[-1, 0,  0]  
kpoff = 0.05 | S[1, 0, -1] -> K[1, 1] + S[-1, 0,  -1]  
kpoff = 0.05 | S[1, 0, 1] -> K[1, 1] + S[-1, 0,  1]  
kpoff = 0.05 | S[-1, 0, 1] -> K[3, 1] + S[-1, 0,  -1]  
kpoff = 0.05 | S[1, 0, 1] -> K[3, 1] + S[1, 0,  -1]  
kpoff = 0.05 | S[1, -1, 0] -> K[1, 1] + S[-1, -1,  0]  
kpoff = 0.05 | S[1, 1, 0] -> K[1, 1] + S[-1, 1,  0]  
kpoff = 0.05 | S[-1, 1, 0] -> K[2, 1] + S[-1, -1,  0]  
kpoff = 0.05 | S[1, 1, 0] -> K[2, 1] + S[1, -1,  0]  
kpoff = 0.05 | S[1, -1, -1] -> K[1, 1] + S[-1, -1,  -1]  
kpoff = 0.05 | S[1, -1, 1] -> K[1, 1] + S[-1, -1,  1]  
kpoff = 0.05 | S[1, 1, -1] -> K[1, 1] + S[-1, 1,  -1]  
kpoff = 0.05 | S[1, 1, 1] -> K[1, 1] + S[-1, 1,  1]  
kpoff = 0.05 | S[-1, 1, -1] -> K[2, 1] + S[-1, -1,  -1]  
kpoff = 0.05 | S[-1, 1, 1] -> K[2, 1] + S[-1, -1,  1]  
kpoff = 0.05 | S[1, 1, -1] -> K[2, 1] + S[1, -1,  -1]  
kpoff = 0.05 | S[1, 1, 1] -> K[2, 1] + S[1, -1,  1]  
kpoff = 0.05 | S[-1, -1, 1] -> K[3, 1] + S[-1, -1,  -1]  
kpoff = 0.05 | S[-1, 1, 1] -> K[3, 1] + S[-1, 1,  -1]  
kpoff = 0.05 | S[1, -1, 1] -> K[3, 1] + S[1, -1,  -1]  
kpoff = 0.05 | S[1, 1, 1] -> K[3, 1] + S[1, 1,  -1]  
kpoff = 0.05 | S[1, 2, 0] -> K[1, 1] + S[-1, 2,  0]  
kpoff = 0.05 | S[-1, 2, 0] -> K[2, 2] + S[-1, -1,  0]  
kpoff = 0.05 | S[1, 2, 0] -> K[2, 2] + S[1, -1,  0]  
kpoff = 0.05 | S[1, 2, -1] -> K[1, 1] + S[-1, 2,  -1]  
kpoff = 0.05 | S[1, 2, 1] -> K[1, 1] + S[-1, 2,  1]  
kpoff = 0.05 | S[-1, 2, -1] -> K[2, 2] + S[-1, -1,  -1]  
kpoff = 0.05 | S[-1, 2, 1] -> K[2, 2] + S[-1, -1,  1]  
kpoff = 0.05 | S[1, 2, -1] -> K[2, 2] + S[1, -1,  -1]  
kpoff = 0.05 | S[1, 2, 1] -> K[2, 2] + S[1, -1,  1]  
kpoff = 0.05 | S[-1, 2, 1] -> K[3, 1] + S[-1, 2,  -1]  
kpoff = 0.05 | S[1, 2, 1] -> K[3, 1] + S[1, 2,  -1]  
kpoff = 0.05 | S[2, 0, 0] -> K[1, 2] + S[-1, 0,  0]  
kpoff = 0.05 | S[2, 0, -1] -> K[1, 2] + S[-1, 0,  -1]  
kpoff = 0.05 | S[2, 0, 1] -> K[1, 2] + S[-1, 0,  1]  
kpoff = 0.05 | S[2, 0, 1] -> K[3, 1] + S[2, 0,  -1]  
kpoff = 0.05 | S[2, -1, 0] -> K[1, 2] + S[-1, -1,  0]  
kpoff = 0.05 | S[2, 1, 0] -> K[1, 2] + S[-1, 1,  0]  
kpoff = 0.05 | S[2, 1, 0] -> K[2, 1] + S[2, -1,  0]  
kpoff = 0.05 | S[2, -1, -1] -> K[1, 2] + S[-1, -1,  -1]  
kpoff = 0.05 | S[2, -1, 1] -> K[1, 2] + S[-1, -1,  1]  
kpoff = 0.05 | S[2, 1, -1] -> K[1, 2] + S[-1, 1,  -1]  
kpoff = 0.05 | S[2, 1, 1] -> K[1, 2] + S[-1, 1,  1]  
kpoff = 0.05 | S[2, 1, -1] -> K[2, 1] + S[2, -1,  -1]  
kpoff = 0.05 | S[2, 1, 1] -> K[2, 1] + S[2, -1,  1]  
kpoff = 0.05 | S[2, -1, 1] -> K[3, 1] + S[2, -1,  -1]  
kpoff = 0.05 | S[2, 1, 1] -> K[3, 1] + S[2, 1,  -1]  
kpoff = 0.05 | S[2, 2, 0] -> K[1, 2] + S[-1, 2,  0]  
kpoff = 0.05 | S[2, 2, 0] -> K[2, 2] + S[2, -1,  0]  
kpoff = 0.05 | S[2, 2, -1] -> K[1, 2] + S[-1, 2,  -1]  
kpoff = 0.05 | S[2, 2, 1] -> K[1, 2] + S[-1, 2,  1]  
kpoff = 0.05 | S[2, 2, -1] -> K[2, 2] + S[2, -1,  -1]  
kpoff = 0.05 | S[2, 2, 1] -> K[2, 2] + S[2, -1,  1]  
kpoff = 0.05 | S[2, 2, 1] -> K[3, 1] + S[2, 2,  -1]  
kpon = 0 | K[1, 1] + S[-1, 0, 0] -> S[1, 0,  0]  
kpon = 0 | K[1, 1] + S[-1, 0, -1] -> S[1, 0,  -1]  
kpon = 0 | K[1, 1] + S[-1, 0, 1] -> S[1, 0,  1]  
kpon = 0 | K[1, 1] + S[-1, -1, 0] -> S[1, -1,  0]  
kpon = 0 | K[1, 1] + S[-1, 1, 0] -> S[1, 1,  0]  
kpon = 0 | K[1, 1] + S[-1, -1, -1] -> S[1, -1,  -1]  
kpon = 0 | K[1, 1] + S[-1, -1, 1] -> S[1, -1,  1]  
kpon = 0 | K[1, 1] + S[-1, 1, -1] -> S[1, 1,  -1]  
kpon = 0 | K[1, 1] + S[-1, 1, 1] -> S[1, 1,  1]  
kpon = 0 | K[1, 1] + S[-1, 2, 0] -> S[1, 2,  0]  
kpon = 0 | K[1, 1] + S[-1, 2, -1] -> S[1, 2,  -1]  
kpon = 0 | K[1, 1] + S[-1, 2, 1] -> S[1, 2,  1]  
kpon = 0 | K[1, 2] + S[-1, 0, 0] -> S[2, 0,  0]  
kpon = 0 | K[1, 2] + S[-1, 0, -1] -> S[2, 0,  -1]  
kpon = 0 | K[1, 2] + S[-1, 0, 1] -> S[2, 0,  1]  
kpon = 0 | K[1, 2] + S[-1, -1, 0] -> S[2, -1,  0]  
kpon = 0 | K[1, 2] + S[-1, 1, 0] -> S[2, 1,  0]  
kpon = 0 | K[1, 2] + S[-1, -1, -1] -> S[2, -1,  -1]  
kpon = 0 | K[1, 2] + S[-1, -1, 1] -> S[2, -1,  1]  
kpon = 0 | K[1, 2] + S[-1, 1, -1] -> S[2, 1,  -1]  
kpon = 0 | K[1, 2] + S[-1, 1, 1] -> S[2, 1,  1]  
kpon = 0 | K[1, 2] + S[-1, 2, 0] -> S[2, 2,  0]  
kpon = 0 | K[1, 2] + S[-1, 2, -1] -> S[2, 2,  -1]  
kpon = 0 | K[1, 2] + S[-1, 2, 1] -> S[2, 2,  1]  
kpon = 0 | K[2, 1] + S[0, -1, 0] -> S[0, 1,  0]  
kpon = 0 | K[2, 1] + S[0, -1, -1] -> S[0, 1,  -1]  
kpon = 0 | K[2, 1] + S[0, -1, 1] -> S[0, 1,  1]  
kpon = 0 | K[2, 1] + S[-1, -1, 0] -> S[-1, 1,  0]  
kpon = 0 | K[2, 1] + S[1, -1, 0] -> S[1, 1,  0]  
kpon = 0 | K[2, 1] + S[-1, -1, -1] -> S[-1, 1,  -1]  
kpon = 0 | K[2, 1] + S[-1, -1, 1] -> S[-1, 1,  1]  
kpon = 0 | K[2, 1] + S[1, -1, -1] -> S[1, 1,  -1]  
kpon = 0 | K[2, 1] + S[1, -1, 1] -> S[1, 1,  1]  
kpon = 0 | K[2, 1] + S[2, -1, 0] -> S[2, 1,  0]  
kpon = 0 | K[2, 1] + S[2, -1, -1] -> S[2, 1,  -1]  
kpon = 0 | K[2, 1] + S[2, -1, 1] -> S[2, 1,  1]  
kpon = 0 | K[2, 2] + S[0, -1, 0] -> S[0, 2,  0]  
kpon = 0 | K[2, 2] + S[0, -1, -1] -> S[0, 2,  -1]  
kpon = 0 | K[2, 2] + S[0, -1, 1] -> S[0, 2,  1]  
kpon = 0 | K[2, 2] + S[-1, -1, 0] -> S[-1, 2,  0]  
kpon = 0 | K[2, 2] + S[1, -1, 0] -> S[1, 2,  0]  
kpon = 0 | K[2, 2] + S[-1, -1, -1] -> S[-1, 2,  -1]  
kpon = 0 | K[2, 2] + S[-1, -1, 1] -> S[-1, 2,  1]  
kpon = 0 | K[2, 2] + S[1, -1, -1] -> S[1, 2,  -1]  
kpon = 0 | K[2, 2] + S[1, -1, 1] -> S[1, 2,  1]  
kpon = 0 | K[2, 2] + S[2, -1, 0] -> S[2, 2,  0]  
kpon = 0 | K[2, 2] + S[2, -1, -1] -> S[2, 2,  -1]  
kpon = 0 | K[2, 2] + S[2, -1, 1] -> S[2, 2,  1]  
kpon = 0 | K[3, 1] + S[0, 0, -1] -> S[0, 0,  1]  
kpon = 0 | K[3, 1] + S[0, -1, -1] -> S[0, -1,  1]  
kpon = 0 | K[3, 1] + S[0, 1, -1] -> S[0, 1,  1]  
kpon = 0 | K[3, 1] + S[0, 2, -1] -> S[0, 2,  1]  
kpon = 0 | K[3, 1] + S[-1, 0, -1] -> S[-1, 0,  1]  
kpon = 0 | K[3, 1] + S[1, 0, -1] -> S[1, 0,  1]  
kpon = 0 | K[3, 1] + S[-1, -1, -1] -> S[-1, -1,  1]  
kpon = 0 | K[3, 1] + S[-1, 1, -1] -> S[-1, 1,  1]  
kpon = 0 | K[3, 1] + S[1, -1, -1] -> S[1, -1,  1]  
kpon = 0 | K[3, 1] + S[1, 1, -1] -> S[1, 1,  1]  
kpon = 0 | K[3, 1] + S[-1, 2, -1] -> S[-1, 2,  1]  
kpon = 0 | K[3, 1] + S[1, 2, -1] -> S[1, 2,  1]  
kpon = 0 | K[3, 1] + S[2, 0, -1] -> S[2, 0,  1]  
kpon = 0 | K[3, 1] + S[2, -1, -1] -> S[2, -1,  1]  
kpon = 0 | K[3, 1] + S[2, 1, -1] -> S[2, 1,  1]  
kpon = 0 | K[3, 1] + S[2, 2, -1] -> S[2, 2,  1]  
Variable | IC   | ODE  
---|---|---  
MAPKP | 0.3 | MAPKP'[t] == -(a8*MAPKP[t]*K[1, 1][t]) - a10*MAPKP[ t]*K[1,
2][t] + d8*K_MAPKP[1, 1][t] + k8*K_MAPKP[ 1, 1][t] + d10*K_MAPKP[1, 2][t] +
k10*K_MAPKP[1,  2][t]  
MEKP | 0.2 | MEKP'[t] == -(a4*MEKP[t]*K[2, 1][t]) - a6*MEKP[t]* K[2, 2][t] +
d4*K_MEKP[2, 1][t] + k4*K_MEKP[2,  1][t] + d6*K_MEKP[2, 2][t] + k6*K_MEKP[2,
2] [t]  
RAFK | 0.1 | RAFK'[t] == -(a1*RAFK[t]*K[3, 0][t]) + d1*K_RAFK[3,  0][t] +
k1*K_RAFK[3, 0][t] - k1a*RAFK[t]*S[-1,  -1, 0][t] - k1a*RAFK[t]*S[-1, 0, 0][t]
-  k1a*RAFK[t]*S[-1, 1, 0][t] - k1a*RAFK[t]*S[-1, 2,  0][t] - k1a*RAFK[t]*S[0,
-1, 0][t] - k1a* RAFK[t]*S[0, 0, 0][t] - k1a*RAFK[t]*S[0, 1, 0][t]  -
k1a*RAFK[t]*S[0, 2, 0][t] - k1a*RAFK[t]*S[1,  -1, 0][t] - k1a*RAFK[t]*S[1, 0,
0][t] -  k1a*RAFK[t]*S[1, 1, 0][t] - k1a*RAFK[t]*S[1, 2,  0][t] -
k1a*RAFK[t]*S[2, -1, 0][t] - k1a* RAFK[t]*S[2, 0, 0][t] - k1a*RAFK[t]*S[2, 1,
0][t]  - k1a*RAFK[t]*S[2, 2, 0][t] + d1a*S_RAFK[-1,  -1, 0][t] + k1*S_RAFK[-1,
-1, 0][t] +  d1a*S_RAFK[-1, 0, 0][t] + k1*S_RAFK[-1, 0,  0][t] +
d1a*S_RAFK[-1, 1, 0][t] + k1*S_RAFK[ -1, 1, 0][t] + d1a*S_RAFK[-1, 2, 0][t] +
k1*S_RAFK[-1, 2, 0][t] + d1a*S_RAFK[0, -1,  0][t] + k1*S_RAFK[0, -1, 0][t] +
d1a*S_RAFK[ 0, 0, 0][t] + k1*S_RAFK[0, 0, 0][t] +  d1a*S_RAFK[0, 1, 0][t] +
k1*S_RAFK[0, 1, 0][ t] + d1a*S_RAFK[0, 2, 0][t] + k1*S_RAFK[0, 2,  0][t] +
d1a*S_RAFK[1, -1, 0][t] + k1*S_RAFK[ 1, -1, 0][t] + d1a*S_RAFK[1, 0, 0][t] +
k1*S_RAFK[1, 0, 0][t] + d1a*S_RAFK[1, 1, 0][ t] + k1*S_RAFK[1, 1, 0][t] +
d1a*S_RAFK[1, 2,  0][t] + k1*S_RAFK[1, 2, 0][t] + d1a*S_RAFK[ 2, -1, 0][t] +
k1*S_RAFK[2, -1, 0][t] +  d1a*S_RAFK[2, 0, 0][t] + k1*S_RAFK[2, 0, 0][ t] +
d1a*S_RAFK[2, 1, 0][t] + k1*S_RAFK[2, 1,  0][t] + d1a*S_RAFK[2, 2, 0][t] +
k1*S_RAFK[ 2, 2, 0][t]  
RAFP | 0.3 | RAFP'[t] == -(a2*RAFP[t]*K[3, 1][t]) + d2*K_RAFP[3,  1][t] +
k2*K_RAFP[3, 1][t]  
K[1, 0] | 0.4 | (K[1, 0])'[t] == -(a7*K[1, 0][t]*K[2, 2][t]) +  d7*K_K[1, 0,
2, 2][t] + k8*K_MAPKP[1, 1][t]  - kon*K[1, 0][t]*S[-1, -1, -1][t] - kon*K[1,
0][t]*S[-1, -1, 0][t] - kon*K[1, 0][t]*S[-1,  -1, 1][t] - kon*K[1, 0][t]*S[-1,
0, -1][t]  - kon*K[1, 0][t]*S[-1, 0, 0][t] - kon*K[1,  0][t]*S[-1, 0, 1][t] -
kon*K[1, 0][t]*S[-1,  1, -1][t] - kon*K[1, 0][t]*S[-1, 1, 0][t]  - kon*K[1,
0][t]*S[-1, 1, 1][t] - kon*K[1,  0][t]*S[-1, 2, -1][t] - kon*K[1, 0][t]*S[-1,
2, 0][t] - kon*K[1, 0][t]*S[-1, 2, 1][t]  + koff*S[0, -1, -1][t] + koff*S[0,
-1,  0][t] + koff*S[0, -1, 1][t] + koff*S[0,  0, -1][t] + koff*S[0, 0, 0][t] +
koff* S[0, 0, 1][t] + koff*S[0, 1, -1][t] +  koff*S[0, 1, 0][t] + koff*S[0, 1,
1][t]  + koff*S[0, 2, -1][t] + koff*S[0, 2, 0] [t] + koff*S[0, 2, 1][t]  
K[1, 1] | 0 | (K[1, 1])'[t] == -(a8*MAPKP[t]*K[1, 1][t]) -  a9*K[1, 1][t]*K[2,
2][t] + k7*K_K[1, 0, 2,  2][t] + d9*K_K[1, 1, 2, 2][t] + d8* K_MAPKP[1, 1][t]
+ k10*K_MAPKP[1, 2][t] - kpon*K[ 1, 1][t]*S[-1, -1, -1][t] - kpon*K[1,
1][t]*S[-1,  -1, 0][t] - kpon*K[1, 1][t]*S[-1, -1, 1][t]  - kpon*K[1,
1][t]*S[-1, 0, -1][t] - kpon*K[ 1, 1][t]*S[-1, 0, 0][t] - kpon*K[1,
1][t]*S[-1,  0, 1][t] - kpon*K[1, 1][t]*S[-1, 1, -1][t]  - kpon*K[1,
1][t]*S[-1, 1, 0][t] - kpon*K[1,  1][t]*S[-1, 1, 1][t] - kpon*K[1, 1][t]*S[-1,
2, -1][t] - kpon*K[1, 1][t]*S[-1, 2, 0][t]  - kpon*K[1, 1][t]*S[-1, 2, 1][t] +
kpoff*S[ 1, -1, -1][t] + kpoff*S[1, -1, 0][t] +  kpoff*S[1, -1, 1][t] +
kpoff*S[1, 0, -1][t]  + kpoff*S[1, 0, 0][t] + kpoff*S[1, 0,  1][t] +
kpoff*S[1, 1, -1][t] + kpoff*S[1,  1, 0][t] + kpoff*S[1, 1, 1][t] + kpoff*
S[1, 2, -1][t] + kpoff*S[1, 2, 0][t] +  kpoff*S[1, 2, 1][t]  
K[1, 2] | 0 | (K[1, 2])'[t] == -(a10*MAPKP[t]*K[1, 2][t]) +  k9*K_K[1, 1, 2,
2][t] + d10*K_MAPKP[1, 2][t]  - kpon*K[1, 2][t]*S[-1, -1, -1][t] - kpon*K[ 1,
2][t]*S[-1, -1, 0][t] - kpon*K[1, 2][t]*S[-1,  -1, 1][t] - kpon*K[1,
2][t]*S[-1, 0, -1][t]  - kpon*K[1, 2][t]*S[-1, 0, 0][t] - kpon*K[1,
2][t]*S[-1, 0, 1][t] - kpon*K[1, 2][t]*S[-1,  1, -1][t] - kpon*K[1,
2][t]*S[-1, 1, 0][t]  - kpon*K[1, 2][t]*S[-1, 1, 1][t] - kpon*K[1,
2][t]*S[-1, 2, -1][t] - kpon*K[1, 2][t]*S[-1,  2, 0][t] - kpon*K[1,
2][t]*S[-1, 2, 1][t]  + kpoff*S[2, -1, -1][t] + kpoff*S[2, -1,  0][t] +
kpoff*S[2, -1, 1][t] + kpoff*S[2,  0, -1][t] + kpoff*S[2, 0, 0][t] +
kpoff*S[2, 0, 1][t] + kpoff*S[2, 1, -1][t]  + kpoff*S[2, 1, 0][t] + kpoff*S[2,
1,  1][t] + kpoff*S[2, 2, -1][t] + kpoff*S[2,  2, 0][t] + kpoff*S[2, 2, 1][t]  
K[2, 0] | 0.2 | (K[2, 0])'[t] == -(a3*K[2, 0][t]*K[3, 1][t]) +  d3*K_K[2, 0,
3, 1][t] + k4*K_MEKP[2, 1][t]  - kon*K[2, 0][t]*S[-1, -1, -1][t] - kon*K[2,
0][t]*S[-1, -1, 0][t] - kon*K[2, 0][t]*S[-1,  -1, 1][t] + koff*S[-1, 0, -1][t]
+  koff*S[-1, 0, 0][t] + koff*S[-1, 0, 1][t]  - kon*K[2, 0][t]*S[0, -1, -1][t]
- kon*K[2,  0][t]*S[0, -1, 0][t] - kon*K[2, 0][t]*S[0, - 1, 1][t] + koff*S[0,
0, -1][t] + koff*S[0,  0, 0][t] + koff*S[0, 0, 1][t] - kon*K[ 2, 0][t]*S[1,
-1, -1][t] - kon*K[2, 0][t]*S[1,  -1, 0][t] - kon*K[2, 0][t]*S[1, -1, 1][t]  +
koff*S[1, 0, -1][t] + koff*S[1, 0, 0] [t] + koff*S[1, 0, 1][t] - kon*K[2,
0][t]*S[ 2, -1, -1][t] - kon*K[2, 0][t]*S[2, -1, 0][t]  - kon*K[2, 0][t]*S[2,
-1, 1][t] + koff*S[2,  0, -1][t] + koff*S[2, 0, 0][t] + koff* S[2, 0, 1][t]  
K[2, 1] | 0 | (K[2, 1])'[t] == -(a4*MEKP[t]*K[2, 1][t]) -  a5*K[2, 1][t]*K[3,
1][t] + k3*K_K[2, 0, 3,  1][t] + d5*K_K[2, 1, 3, 1][t] + d4* K_MEKP[2, 1][t] +
k6*K_MEKP[2, 2][t] - kpon*K[2,  1][t]*S[-1, -1, -1][t] - kpon*K[2, 1][t]*S[-1,
-1, 0][t] - kpon*K[2, 1][t]*S[-1, -1, 1][t]  + kpoff*S[-1, 1, -1][t] +
kpoff*S[-1, 1,  0][t] + kpoff*S[-1, 1, 1][t] - kpon*K[2,  1][t]*S[0, -1,
-1][t] - kpon*K[2, 1][t]*S[0,  -1, 0][t] - kpon*K[2, 1][t]*S[0, -1, 1][t]  +
kpoff*S[0, 1, -1][t] + kpoff*S[0, 1,  0][t] + kpoff*S[0, 1, 1][t] - kpon*K[2,
1][t]*S[1, -1, -1][t] - kpon*K[2, 1][t]*S[1,  -1, 0][t] - kpon*K[2, 1][t]*S[1,
-1, 1][t]  + kpoff*S[1, 1, -1][t] + kpoff*S[1, 1,  0][t] + kpoff*S[1, 1, 1][t]
- kpon*K[2,  1][t]*S[2, -1, -1][t] - kpon*K[2, 1][t]*S[2,  -1, 0][t] -
kpon*K[2, 1][t]*S[2, -1, 1][t]  + kpoff*S[2, 1, -1][t] + kpoff*S[2, 1,  0][t]
+ kpoff*S[2, 1, 1][t]  
K[2, 2] | 0 | (K[2, 2])'[t] == -(a6*MEKP[t]*K[2, 2][t]) -  a7*K[1, 0][t]*K[2,
2][t] - a9*K[1, 1][t]*K[2,  2][t] + d7*K_K[1, 0, 2, 2][t] + k7*K_K[ 1, 0, 2,
2][t] + d9*K_K[1, 1, 2, 2][t]  + k9*K_K[1, 1, 2, 2][t] + k5*K_K[2, 1,  3,
1][t] + d6*K_MEKP[2, 2][t] - kpon*K[2,  2][t]*S[-1, -1, -1][t] - kpon*K[2,
2][t]*S[-1,  -1, 0][t] - kpon*K[2, 2][t]*S[-1, -1, 1][t]  + kpoff*S[-1, 2,
-1][t] + kpoff*S[-1, 2,  0][t] + kpoff*S[-1, 2, 1][t] - kpon*K[2,  2][t]*S[0,
-1, -1][t] - kpon*K[2, 2][t]*S[0,  -1, 0][t] - kpon*K[2, 2][t]*S[0, -1, 1][t]
+ kpoff*S[0, 2, -1][t] + kpoff*S[0, 2,  0][t] + kpoff*S[0, 2, 1][t] -
kpon*K[2,  2][t]*S[1, -1, -1][t] - kpon*K[2, 2][t]*S[1,  -1, 0][t] - kpon*K[2,
2][t]*S[1, -1, 1][t]  + kpoff*S[1, 2, -1][t] + kpoff*S[1, 2,  0][t] +
kpoff*S[1, 2, 1][t] - kpon*K[2,  2][t]*S[2, -1, -1][t] - kpon*K[2, 2][t]*S[2,
-1, 0][t] - kpon*K[2, 2][t]*S[2, -1, 1][t]  + kpoff*S[2, 2, -1][t] +
kpoff*S[2, 2,  0][t] + kpoff*S[2, 2, 1][t]  
K[3, 0] | 0.3 | (K[3, 0])'[t] == -(a1*RAFK[t]*K[3, 0][t]) +  d1*K_RAFK[3,
0][t] + k2*K_RAFP[3, 1][t] -  kon*K[3, 0][t]*S[-1, -1, -1][t] + koff*S[-1,
-1, 0][t] - kon*K[3, 0][t]*S[-1, 0, -1][t]  + koff*S[-1, 0, 0][t] - kon*K[3,
0][t]*S[-1,  1, -1][t] + koff*S[-1, 1, 0][t] - kon* K[3, 0][t]*S[-1, 2, -1][t]
+ koff*S[-1, 2, 0] [t] - kon*K[3, 0][t]*S[0, -1, -1][t] + koff* S[0, -1, 0][t]
- kon*K[3, 0][t]*S[0, 0, -1][ t] + koff*S[0, 0, 0][t] - kon*K[3, 0][t]*S[0,
1, -1][t] + koff*S[0, 1, 0][t] - kon*K[ 3, 0][t]*S[0, 2, -1][t] + koff*S[0, 2,
0][t]  - kon*K[3, 0][t]*S[1, -1, -1][t] + koff*S[1,  -1, 0][t] - kon*K[3,
0][t]*S[1, 0, -1][t]  + koff*S[1, 0, 0][t] - kon*K[3, 0][t]*S[1,  1, -1][t] +
koff*S[1, 1, 0][t] - kon*K[ 3, 0][t]*S[1, 2, -1][t] + koff*S[1, 2, 0][t]  -
kon*K[3, 0][t]*S[2, -1, -1][t] + koff*S[2,  -1, 0][t] - kon*K[3, 0][t]*S[2, 0,
-1][t]  + koff*S[2, 0, 0][t] - kon*K[3, 0][t]*S[2,  1, -1][t] + koff*S[2, 1,
0][t] - kon*K[ 3, 0][t]*S[2, 2, -1][t] + koff*S[2, 2, 0][t]  
K[3, 1] | 0 | (K[3, 1])'[t] == -(a2*RAFP[t]*K[3, 1][t]) -  a3*K[2, 0][t]*K[3,
1][t] - a5*K[2, 1][t]*K[3,  1][t] + d3*K_K[2, 0, 3, 1][t] + k3*K_K[ 2, 0, 3,
1][t] + d5*K_K[2, 1, 3, 1][t]  + k5*K_K[2, 1, 3, 1][t] + k1*K_RAFK[3,  0][t] +
d2*K_RAFP[3, 1][t] - kpon*K[3, 1][t] *S[-1, -1, -1][t] + kpoff*S[-1, -1, 1][t]
-  kpon*K[3, 1][t]*S[-1, 0, -1][t] + kpoff*S[-1,  0, 1][t] - kpon*K[3,
1][t]*S[-1, 1, -1][t]  + kpoff*S[-1, 1, 1][t] - kpon*K[3, 1][t]*S[- 1, 2,
-1][t] + kpoff*S[-1, 2, 1][t] -  kpon*K[3, 1][t]*S[0, -1, -1][t] + kpoff*S[0,
-1, 1][t] - kpon*K[3, 1][t]*S[0, 0, -1][t]  + kpoff*S[0, 0, 1][t] - kpon*K[3,
1][t]*S[0,  1, -1][t] + kpoff*S[0, 1, 1][t] - kpon* K[3, 1][t]*S[0, 2, -1][t]
+ kpoff*S[0, 2, 1][ t] - kpon*K[3, 1][t]*S[1, -1, -1][t] + kpoff* S[1, -1,
1][t] - kpon*K[3, 1][t]*S[1, 0, -1][ t] + kpoff*S[1, 0, 1][t] - kpon*K[3,
1][t]*S[ 1, 1, -1][t] + kpoff*S[1, 1, 1][t] -  kpon*K[3, 1][t]*S[1, 2, -1][t]
+ kpoff*S[1,  2, 1][t] - kpon*K[3, 1][t]*S[2, -1, -1][t]  + kpoff*S[2, -1,
1][t] - kpon*K[3, 1][t]*S[ 2, 0, -1][t] + kpoff*S[2, 0, 1][t] -  kpon*K[3,
1][t]*S[2, 1, -1][t] + kpoff*S[2,  1, 1][t] - kpon*K[3, 1][t]*S[2, 2, -1][t]
+ kpoff*S[2, 2, 1][t]  
K_K[1, 0, 2, 2] | 0 | (K_K[1, 0, 2, 2])'[t] == a7*K[1, 0][t]*K[2,  2][t] -
d7*K_K[1, 0, 2, 2][t] - k7*K_K[ 1, 0, 2, 2][t]  
K_K[1, 1, 2, 2] | 0 | (K_K[1, 1, 2, 2])'[t] == a9*K[1, 1][t]*K[2,  2][t] -
d9*K_K[1, 1, 2, 2][t] - k9*K_K[ 1, 1, 2, 2][t]  
K_K[2, 0, 3, 1] | 0 | (K_K[2, 0, 3, 1])'[t] == a3*K[2, 0][t]*K[3,  1][t] -
d3*K_K[2, 0, 3, 1][t] - k3*K_K[ 2, 0, 3, 1][t]  
K_K[2, 1, 3, 1] | 0 | (K_K[2, 1, 3, 1])'[t] == a5*K[2, 1][t]*K[3,  1][t] -
d5*K_K[2, 1, 3, 1][t] - k5*K_K[ 2, 1, 3, 1][t]  
K_MAPKP[1, 1] | 0 | (K_MAPKP[1, 1])'[t] == a8*MAPKP[t]*K[1, 1][t] -
d8*K_MAPKP[1, 1][t] - k8*K_MAPKP[1, 1][t]  
K_MAPKP[1, 2] | 0 | (K_MAPKP[1, 2])'[t] == a10*MAPKP[t]*K[1, 2][t] -
d10*K_MAPKP[1, 2][t] - k10*K_MAPKP[1, 2][t]  
K_MEKP[2, 1] | 0 | (K_MEKP[2, 1])'[t] == a4*MEKP[t]*K[2, 1][t] -  d4*K_MEKP[2,
1][t] - k4*K_MEKP[2, 1][t]  
K_MEKP[2, 2] | 0 | (K_MEKP[2, 2])'[t] == a6*MEKP[t]*K[2, 2][t] -  d6*K_MEKP[2,
2][t] - k6*K_MEKP[2, 2][t]  
K_RAFK[3, 0] | 0 | (K_RAFK[3, 0])'[t] == a1*RAFK[t]*K[3, 0][t] -  d1*K_RAFK[3,
0][t] - k1*K_RAFK[3, 0][t]  
K_RAFP[3, 1] | 0 | (K_RAFP[3, 1])'[t] == a2*RAFP[t]*K[3, 1][t] -  d2*K_RAFP[3,
1][t] - k2*K_RAFP[3, 1][t]  
S[-1, -1, -1] | 0.1 | (S[-1, -1, -1])'[t] == -(kon*K[1, 0][t]*S[-1,  -1,
-1][t]) - kpon*K[1, 1][t]*S[-1, -1, -1][ t] - kpon*K[1, 2][t]*S[-1, -1, -1][t]
- kon* K[2, 0][t]*S[-1, -1, -1][t] - kpon*K[2, 1][t]*S[- 1, -1, -1][t] -
kpon*K[2, 2][t]*S[-1, -1, -1] [t] - kon*K[3, 0][t]*S[-1, -1, -1][t] - kpon*
K[3, 1][t]*S[-1, -1, -1][t] + koff*S[-1, -1,  0][t] + kpoff*S[-1, -1, 1][t] +
koff*S[-1,  0, -1][t] + kpoff*S[-1, 1, -1][t] +  kpoff*S[-1, 2, -1][t] +
koff*S[0, -1, -1][t]  + kpoff*S[1, -1, -1][t] + kpoff*S[2, -1,  -1][t]  
S[-1, -1, 0] | 0 | (S[-1, -1, 0])'[t] == kon*K[3, 0][t]*S[-1, -1,  -1][t] -
koff*S[-1, -1, 0][t] - k1a*RAFK[t]* S[-1, -1, 0][t] - kon*K[1, 0][t]*S[-1, -1,
0] [t] - kpon*K[1, 1][t]*S[-1, -1, 0][t] - kpon* K[1, 2][t]*S[-1, -1, 0][t] -
kon*K[2, 0][t]*S[-1,  -1, 0][t] - kpon*K[2, 1][t]*S[-1, -1, 0][t]  - kpon*K[2,
2][t]*S[-1, -1, 0][t] + koff*S[- 1, 0, 0][t] + kpoff*S[-1, 1, 0][t] +
kpoff*S[-1, 2, 0][t] + koff*S[0, -1, 0][t]  + kpoff*S[1, -1, 0][t] +
kpoff*S[2, -1,  0][t] + d1a*S_RAFK[-1, -1, 0][t]  
S[-1, -1, 1] | 0 | (S[-1, -1, 1])'[t] == kpon*K[3, 1][t]*S[-1, - 1, -1][t] -
kpoff*S[-1, -1, 1][t] - kon*K[1,  0][t]*S[-1, -1, 1][t] - kpon*K[1,
1][t]*S[-1,  -1, 1][t] - kpon*K[1, 2][t]*S[-1, -1, 1][t]  - kon*K[2,
0][t]*S[-1, -1, 1][t] - kpon*K[2,  1][t]*S[-1, -1, 1][t] - kpon*K[2,
2][t]*S[-1,  -1, 1][t] + koff*S[-1, 0, 1][t] +  kpoff*S[-1, 1, 1][t] +
kpoff*S[-1, 2, 1][t]  + koff*S[0, -1, 1][t] + kpoff*S[1, -1,  1][t] +
kpoff*S[2, -1, 1][t] + k1*S_RAFK[-1,  -1, 0][t]  
S[-1, 0, -1] | 0 | (S[-1, 0, -1])'[t] == kon*K[2, 0][t]*S[-1, -1,  -1][t] -
koff*S[-1, 0, -1][t] - kon*K[1,  0][t]*S[-1, 0, -1][t] - kpon*K[1, 1][t]*S[-1,
0, -1][t] - kpon*K[1, 2][t]*S[-1, 0, -1][t]  - kon*K[3, 0][t]*S[-1, 0, -1][t]
- kpon*K[3,  1][t]*S[-1, 0, -1][t] + koff*S[-1, 0, 0][t]  + kpoff*S[-1, 0,
1][t] + koff*S[0, 0, - 1][t] + kpoff*S[1, 0, -1][t] + kpoff*S[2, 0,  -1][t]  
S[-1, 0, 0] | 0 | (S[-1, 0, 0])'[t] == kon*K[2, 0][t]*S[-1, -1,  0][t] +
kon*K[3, 0][t]*S[-1, 0, -1][t] -  2*koff*S[-1, 0, 0][t] - k1a*RAFK[t]*S[-1, 0,
0][t] - kon*K[1, 0][t]*S[-1, 0, 0][t] -  kpon*K[1, 1][t]*S[-1, 0, 0][t] -
kpon*K[1,  2][t]*S[-1, 0, 0][t] + koff*S[0, 0, 0][t]  + kpoff*S[1, 0, 0][t] +
kpoff*S[2, 0,  0][t] + d1a*S_RAFK[-1, 0, 0][t]  
S[-1, 0, 1] | 0 | (S[-1, 0, 1])'[t] == kon*K[2, 0][t]*S[-1, -1,  1][t] +
kpon*K[3, 1][t]*S[-1, 0, -1][t] -  k3*S[-1, 0, 1][t] - koff*S[-1, 0, 1][t]  -
kpoff*S[-1, 0, 1][t] - kon*K[1, 0][t]*S[- 1, 0, 1][t] - kpon*K[1, 1][t]*S[-1,
0, 1][t]  - kpon*K[1, 2][t]*S[-1, 0, 1][t] + koff*S[0,  0, 1][t] + kpoff*S[1,
0, 1][t] + kpoff* S[2, 0, 1][t] + k1*S_RAFK[-1, 0, 0][t]  
S[-1, 1, -1] | 0 | (S[-1, 1, -1])'[t] == kpon*K[2, 1][t]*S[-1, - 1, -1][t] -
kpoff*S[-1, 1, -1][t] - kon*K[1,  0][t]*S[-1, 1, -1][t] - kpon*K[1,
1][t]*S[-1,  1, -1][t] - kpon*K[1, 2][t]*S[-1, 1, -1][t]  - kon*K[3,
0][t]*S[-1, 1, -1][t] - kpon*K[3,  1][t]*S[-1, 1, -1][t] + koff*S[-1, 1, 0][t]
+ kpoff*S[-1, 1, 1][t] + koff*S[0, 1, - 1][t] + kpoff*S[1, 1, -1][t] +
kpoff*S[2, 1,  -1][t]  
S[-1, 1, 0] | 0 | (S[-1, 1, 0])'[t] == kpon*K[2, 1][t]*S[-1, -1,  0][t] +
kon*K[3, 0][t]*S[-1, 1, -1][t] -  koff*S[-1, 1, 0][t] - kpoff*S[-1, 1, 0][t]
- k1a*RAFK[t]*S[-1, 1, 0][t] - kon*K[1, 0][ t]*S[-1, 1, 0][t] - kpon*K[1,
1][t]*S[-1, 1,  0][t] - kpon*K[1, 2][t]*S[-1, 1, 0][t] +  koff*S[0, 1, 0][t] +
kpoff*S[1, 1, 0][t]  + kpoff*S[2, 1, 0][t] + d1a*S_RAFK[-1, 1,  0][t]  
S[-1, 1, 1] | 0 | (S[-1, 1, 1])'[t] == kpon*K[2, 1][t]*S[-1, -1,  1][t] +
k3*S[-1, 0, 1][t] + kpon*K[3,  1][t]*S[-1, 1, -1][t] - k5a*S[-1, 1, 1][t]  -
2*kpoff*S[-1, 1, 1][t] - kon*K[1, 0][t]*S[ -1, 1, 1][t] - kpon*K[1,
1][t]*S[-1, 1, 1][t]  - kpon*K[1, 2][t]*S[-1, 1, 1][t] + koff*S[0,  1, 1][t] +
kpoff*S[1, 1, 1][t] + kpoff* S[2, 1, 1][t] + k1*S_RAFK[-1, 1, 0][t]  
S[-1, 2, -1] | 0 | (S[-1, 2, -1])'[t] == kpon*K[2, 2][t]*S[-1, - 1, -1][t] -
kpoff*S[-1, 2, -1][t] - kon*K[1,  0][t]*S[-1, 2, -1][t] - kpon*K[1,
1][t]*S[-1,  2, -1][t] - kpon*K[1, 2][t]*S[-1, 2, -1][t]  - kon*K[3,
0][t]*S[-1, 2, -1][t] - kpon*K[3,  1][t]*S[-1, 2, -1][t] + koff*S[-1, 2, 0][t]
+ kpoff*S[-1, 2, 1][t] + koff*S[0, 2, - 1][t] + kpoff*S[1, 2, -1][t] +
kpoff*S[2, 2,  -1][t]  
S[-1, 2, 0] | 0 | (S[-1, 2, 0])'[t] == kpon*K[2, 2][t]*S[-1, -1,  0][t] +
kon*K[3, 0][t]*S[-1, 2, -1][t] -  koff*S[-1, 2, 0][t] - kpoff*S[-1, 2, 0][t]
- k1a*RAFK[t]*S[-1, 2, 0][t] - kon*K[1, 0][ t]*S[-1, 2, 0][t] - kpon*K[1,
1][t]*S[-1, 2,  0][t] - kpon*K[1, 2][t]*S[-1, 2, 0][t] +  koff*S[0, 2, 0][t] +
kpoff*S[1, 2, 0][t]  + kpoff*S[2, 2, 0][t] + d1a*S_RAFK[-1, 2,  0][t]  
S[-1, 2, 1] | 0 | (S[-1, 2, 1])'[t] == kpon*K[2, 2][t]*S[-1, -1,  1][t] +
k5a*S[-1, 1, 1][t] + kpon*K[3,  1][t]*S[-1, 2, -1][t] - 2*kpoff*S[-1, 2, 1][
t] - kon*K[1, 0][t]*S[-1, 2, 1][t] - kpon*K[ 1, 1][t]*S[-1, 2, 1][t] -
kpon*K[1, 2][t]*S[-1,  2, 1][t] + koff*S[0, 2, 1][t] + kpoff* S[1, 2, 1][t] +
kpoff*S[2, 2, 1][t] +  k1*S_RAFK[-1, 2, 0][t]  
S[0, -1, -1] | 0 | (S[0, -1, -1])'[t] == kon*K[1, 0][t]*S[-1, -1,  -1][t] -
koff*S[0, -1, -1][t] - kon*K[2,  0][t]*S[0, -1, -1][t] - kpon*K[2, 1][t]*S[0,
-1, -1][t] - kpon*K[2, 2][t]*S[0, -1, -1][t]  - kon*K[3, 0][t]*S[0, -1, -1][t]
- kpon*K[3,  1][t]*S[0, -1, -1][t] + koff*S[0, -1, 0][t]  + kpoff*S[0, -1,
1][t] + koff*S[0, 0, - 1][t] + kpoff*S[0, 1, -1][t] + kpoff*S[0, 2,  -1][t]  
S[0, -1, 0] | 0 | (S[0, -1, 0])'[t] == kon*K[1, 0][t]*S[-1, -1,  0][t] +
kon*K[3, 0][t]*S[0, -1, -1][t] -  2*koff*S[0, -1, 0][t] - k1a*RAFK[t]*S[0, -1,
0][t] - kon*K[2, 0][t]*S[0, -1, 0][t] -  kpon*K[2, 1][t]*S[0, -1, 0][t] -
kpon*K[2,  2][t]*S[0, -1, 0][t] + koff*S[0, 0, 0][t]  + kpoff*S[0, 1, 0][t] +
kpoff*S[0, 2,  0][t] + d1a*S_RAFK[0, -1, 0][t]  
S[0, -1, 1] | 0 | (S[0, -1, 1])'[t] == kon*K[1, 0][t]*S[-1, -1,  1][t] +
kpon*K[3, 1][t]*S[0, -1, -1][t] -  koff*S[0, -1, 1][t] - kpoff*S[0, -1, 1][t]
- kon*K[2, 0][t]*S[0, -1, 1][t] - kpon*K[2,  1][t]*S[0, -1, 1][t] - kpon*K[2,
2][t]*S[0,  -1, 1][t] + koff*S[0, 0, 1][t] + kpoff* S[0, 1, 1][t] + kpoff*S[0,
2, 1][t] +  k1*S_RAFK[0, -1, 0][t]  
S[0, 0, -1] | 0 | (S[0, 0, -1])'[t] == kon*K[1, 0][t]*S[-1, 0,  -1][t] +
kon*K[2, 0][t]*S[0, -1, -1][t] -  2*koff*S[0, 0, -1][t] - kon*K[3, 0][t]*S[0,
0, -1][t] - kpon*K[3, 1][t]*S[0, 0, -1][t]  + koff*S[0, 0, 0][t] + kpoff*S[0,
0, 1] [t]  
S[0, 0, 0] | 0 | (S[0, 0, 0])'[t] == kon*K[1, 0][t]*S[-1, 0,  0][t] + kon*K[2,
0][t]*S[0, -1, 0][t] +  kon*K[3, 0][t]*S[0, 0, -1][t] - 3*koff*S[0,  0, 0][t]
- k1a*RAFK[t]*S[0, 0, 0][t] +  d1a*S_RAFK[0, 0, 0][t]  
S[0, 0, 1] | 0 | (S[0, 0, 1])'[t] == kon*K[1, 0][t]*S[-1, 0,  1][t] + kon*K[2,
0][t]*S[0, -1, 1][t] +  kpon*K[3, 1][t]*S[0, 0, -1][t] - k3*S[0, 0,  1][t] -
2*koff*S[0, 0, 1][t] - kpoff*S[0,  0, 1][t] + k1*S_RAFK[0, 0, 0][t]  
S[0, 1, -1] | 0 | (S[0, 1, -1])'[t] == kon*K[1, 0][t]*S[-1, 1,  -1][t] +
kpon*K[2, 1][t]*S[0, -1, -1][t] -  koff*S[0, 1, -1][t] - kpoff*S[0, 1, -1][t]
- kon*K[3, 0][t]*S[0, 1, -1][t] - kpon*K[3,  1][t]*S[0, 1, -1][t] + koff*S[0,
1, 0][t]  + kpoff*S[0, 1, 1][t]  
S[0, 1, 0] | 0 | (S[0, 1, 0])'[t] == kon*K[1, 0][t]*S[-1, 1,  0][t] +
kpon*K[2, 1][t]*S[0, -1, 0][t] +  kon*K[3, 0][t]*S[0, 1, -1][t] - 2*koff*S[0,
1, 0][t] - kpoff*S[0, 1, 0][t] - k1a* RAFK[t]*S[0, 1, 0][t] + d1a*S_RAFK[0, 1,
0][t]  
S[0, 1, 1] | 0 | (S[0, 1, 1])'[t] == kon*K[1, 0][t]*S[-1, 1,  1][t] +
kpon*K[2, 1][t]*S[0, -1, 1][t] +  k3*S[0, 0, 1][t] + kpon*K[3, 1][t]*S[0, 1,
-1][t] - k5a*S[0, 1, 1][t] - koff*S[0,  1, 1][t] - 2*kpoff*S[0, 1, 1][t] + k1*
S_RAFK[0, 1, 0][t]  
S[0, 2, -1] | 0 | (S[0, 2, -1])'[t] == kon*K[1, 0][t]*S[-1, 2,  -1][t] +
kpon*K[2, 2][t]*S[0, -1, -1][t] -  k7*S[0, 2, -1][t] - koff*S[0, 2, -1][t]  -
kpoff*S[0, 2, -1][t] - kon*K[3, 0][t]*S[0,  2, -1][t] - kpon*K[3, 1][t]*S[0,
2, -1][t]  + koff*S[0, 2, 0][t] + kpoff*S[0, 2, 1] [t]  
S[0, 2, 0] | 0 | (S[0, 2, 0])'[t] == kon*K[1, 0][t]*S[-1, 2,  0][t] +
kpon*K[2, 2][t]*S[0, -1, 0][t] +  kon*K[3, 0][t]*S[0, 2, -1][t] - k7*S[0, 2,
0][t] - 2*koff*S[0, 2, 0][t] - kpoff*S[0,  2, 0][t] - k1a*RAFK[t]*S[0, 2,
0][t] +  d1a*S_RAFK[0, 2, 0][t]  
S[0, 2, 1] | 0 | (S[0, 2, 1])'[t] == kon*K[1, 0][t]*S[-1, 2,  1][t] +
kpon*K[2, 2][t]*S[0, -1, 1][t] +  k5a*S[0, 1, 1][t] + kpon*K[3, 1][t]*S[0, 2,
-1][t] - k7*S[0, 2, 1][t] - koff*S[0,  2, 1][t] - 2*kpoff*S[0, 2, 1][t] + k1*
S_RAFK[0, 2, 0][t]  
S[1, -1, -1] | 0 | (S[1, -1, -1])'[t] == kpon*K[1, 1][t]*S[-1, - 1, -1][t] -
kpoff*S[1, -1, -1][t] - kon*K[2,  0][t]*S[1, -1, -1][t] - kpon*K[2, 1][t]*S[1,
-1, -1][t] - kpon*K[2, 2][t]*S[1, -1, -1][t]  - kon*K[3, 0][t]*S[1, -1, -1][t]
- kpon*K[3,  1][t]*S[1, -1, -1][t] + koff*S[1, -1, 0][t]  + kpoff*S[1, -1,
1][t] + koff*S[1, 0, - 1][t] + kpoff*S[1, 1, -1][t] + kpoff*S[1, 2,  -1][t]  
S[1, -1, 0] | 0 | (S[1, -1, 0])'[t] == kpon*K[1, 1][t]*S[-1, -1,  0][t] +
kon*K[3, 0][t]*S[1, -1, -1][t] -  koff*S[1, -1, 0][t] - kpoff*S[1, -1, 0][t]
- k1a*RAFK[t]*S[1, -1, 0][t] - kon*K[2, 0][ t]*S[1, -1, 0][t] - kpon*K[2,
1][t]*S[1, -1,  0][t] - kpon*K[2, 2][t]*S[1, -1, 0][t] +  koff*S[1, 0, 0][t] +
kpoff*S[1, 1, 0][t]  + kpoff*S[1, 2, 0][t] + d1a*S_RAFK[1, -1,  0][t]  
S[1, -1, 1] | 0 | (S[1, -1, 1])'[t] == kpon*K[1, 1][t]*S[-1, -1,  1][t] +
kpon*K[3, 1][t]*S[1, -1, -1][t] -  2*kpoff*S[1, -1, 1][t] - kon*K[2,
0][t]*S[1,  -1, 1][t] - kpon*K[2, 1][t]*S[1, -1, 1][t]  - kpon*K[2, 2][t]*S[1,
-1, 1][t] + koff*S[1,  0, 1][t] + kpoff*S[1, 1, 1][t] + kpoff* S[1, 2, 1][t] +
k1*S_RAFK[1, -1, 0][t]  
S[1, 0, -1] | 0 | (S[1, 0, -1])'[t] == kpon*K[1, 1][t]*S[-1, 0,  -1][t] +
kon*K[2, 0][t]*S[1, -1, -1][t] -  koff*S[1, 0, -1][t] - kpoff*S[1, 0, -1][t]
- kon*K[3, 0][t]*S[1, 0, -1][t] - kpon*K[3,  1][t]*S[1, 0, -1][t] + koff*S[1,
0, 0][t]  + kpoff*S[1, 0, 1][t]  
S[1, 0, 0] | 0 | (S[1, 0, 0])'[t] == kpon*K[1, 1][t]*S[-1, 0,  0][t] +
kon*K[2, 0][t]*S[1, -1, 0][t] +  kon*K[3, 0][t]*S[1, 0, -1][t] - 2*koff*S[1,
0, 0][t] - kpoff*S[1, 0, 0][t] - k1a* RAFK[t]*S[1, 0, 0][t] + d1a*S_RAFK[1, 0,
0][t]  
S[1, 0, 1] | 0 | (S[1, 0, 1])'[t] == kpon*K[1, 1][t]*S[-1, 0,  1][t] +
kon*K[2, 0][t]*S[1, -1, 1][t] +  kpon*K[3, 1][t]*S[1, 0, -1][t] - k3*S[1, 0,
1][t] - koff*S[1, 0, 1][t] - 2*kpoff*S[1,  0, 1][t] + k1*S_RAFK[1, 0, 0][t]  
S[1, 1, -1] | 0 | (S[1, 1, -1])'[t] == kpon*K[1, 1][t]*S[-1, 1,  -1][t] +
kpon*K[2, 1][t]*S[1, -1, -1][t] -  2*kpoff*S[1, 1, -1][t] - kon*K[3,
0][t]*S[1,  1, -1][t] - kpon*K[3, 1][t]*S[1, 1, -1][t]  + koff*S[1, 1, 0][t] +
kpoff*S[1, 1, 1] [t]  
S[1, 1, 0] | 0 | (S[1, 1, 0])'[t] == kpon*K[1, 1][t]*S[-1, 1,  0][t] +
kpon*K[2, 1][t]*S[1, -1, 0][t] +  kon*K[3, 0][t]*S[1, 1, -1][t] - koff*S[1, 1,
0][t] - 2*kpoff*S[1, 1, 0][t] - k1a*RAFK[t]* S[1, 1, 0][t] + d1a*S_RAFK[1, 1,
0][t]  
S[1, 1, 1] | 0 | (S[1, 1, 1])'[t] == kpon*K[1, 1][t]*S[-1, 1,  1][t] +
kpon*K[2, 1][t]*S[1, -1, 1][t] +  k3*S[1, 0, 1][t] + kpon*K[3, 1][t]*S[1, 1,
-1][t] - k5a*S[1, 1, 1][t] - 3*kpoff*S[1,  1, 1][t] + k1*S_RAFK[1, 1, 0][t]  
S[1, 2, -1] | 0 | (S[1, 2, -1])'[t] == kpon*K[1, 1][t]*S[-1, 2,  -1][t] +
k7*S[0, 2, -1][t] + kpon*K[2,  2][t]*S[1, -1, -1][t] - k9a*S[1, 2, -1][t]  -
2*kpoff*S[1, 2, -1][t] - kon*K[3, 0][t]*S[ 1, 2, -1][t] - kpon*K[3, 1][t]*S[1,
2, -1][t]  + koff*S[1, 2, 0][t] + kpoff*S[1, 2, 1] [t]  
S[1, 2, 0] | 0 | (S[1, 2, 0])'[t] == kpon*K[1, 1][t]*S[-1, 2,  0][t] + k7*S[0,
2, 0][t] + kpon*K[2, 2] [t]*S[1, -1, 0][t] + kon*K[3, 0][t]*S[1, 2, - 1][t] -
k9a*S[1, 2, 0][t] - koff*S[1, 2,  0][t] - 2*kpoff*S[1, 2, 0][t] - k1a*RAFK[t]*
S[1, 2, 0][t] + d1a*S_RAFK[1, 2, 0][t]  
S[1, 2, 1] | 0 | (S[1, 2, 1])'[t] == kpon*K[1, 1][t]*S[-1, 2,  1][t] + k7*S[0,
2, 1][t] + kpon*K[2, 2] [t]*S[1, -1, 1][t] + k5a*S[1, 1, 1][t] +  kpon*K[3,
1][t]*S[1, 2, -1][t] - k9a*S[1, 2,  1][t] - 3*kpoff*S[1, 2, 1][t] +
k1*S_RAFK[1,  2, 0][t]  
S[2, -1, -1] | 0 | (S[2, -1, -1])'[t] == kpon*K[1, 2][t]*S[-1, - 1, -1][t] -
kpoff*S[2, -1, -1][t] - kon*K[2,  0][t]*S[2, -1, -1][t] - kpon*K[2, 1][t]*S[2,
-1, -1][t] - kpon*K[2, 2][t]*S[2, -1, -1][t]  - kon*K[3, 0][t]*S[2, -1, -1][t]
- kpon*K[3,  1][t]*S[2, -1, -1][t] + koff*S[2, -1, 0][t]  + kpoff*S[2, -1,
1][t] + koff*S[2, 0, - 1][t] + kpoff*S[2, 1, -1][t] + kpoff*S[2, 2,  -1][t]  
S[2, -1, 0] | 0 | (S[2, -1, 0])'[t] == kpon*K[1, 2][t]*S[-1, -1,  0][t] +
kon*K[3, 0][t]*S[2, -1, -1][t] -  koff*S[2, -1, 0][t] - kpoff*S[2, -1, 0][t]
- k1a*RAFK[t]*S[2, -1, 0][t] - kon*K[2, 0][ t]*S[2, -1, 0][t] - kpon*K[2,
1][t]*S[2, -1,  0][t] - kpon*K[2, 2][t]*S[2, -1, 0][t] +  koff*S[2, 0, 0][t] +
kpoff*S[2, 1, 0][t]  + kpoff*S[2, 2, 0][t] + d1a*S_RAFK[2, -1,  0][t]  
S[2, -1, 1] | 0 | (S[2, -1, 1])'[t] == kpon*K[1, 2][t]*S[-1, -1,  1][t] +
kpon*K[3, 1][t]*S[2, -1, -1][t] -  2*kpoff*S[2, -1, 1][t] - kon*K[2,
0][t]*S[2,  -1, 1][t] - kpon*K[2, 1][t]*S[2, -1, 1][t]  - kpon*K[2, 2][t]*S[2,
-1, 1][t] + koff*S[2,  0, 1][t] + kpoff*S[2, 1, 1][t] + kpoff* S[2, 2, 1][t] +
k1*S_RAFK[2, -1, 0][t]  
S[2, 0, -1] | 0 | (S[2, 0, -1])'[t] == kpon*K[1, 2][t]*S[-1, 0,  -1][t] +
kon*K[2, 0][t]*S[2, -1, -1][t] -  koff*S[2, 0, -1][t] - kpoff*S[2, 0, -1][t]
- kon*K[3, 0][t]*S[2, 0, -1][t] - kpon*K[3,  1][t]*S[2, 0, -1][t] + koff*S[2,
0, 0][t]  + kpoff*S[2, 0, 1][t]  
S[2, 0, 0] | 0 | (S[2, 0, 0])'[t] == kpon*K[1, 2][t]*S[-1, 0,  0][t] +
kon*K[2, 0][t]*S[2, -1, 0][t] +  kon*K[3, 0][t]*S[2, 0, -1][t] - 2*koff*S[2,
0, 0][t] - kpoff*S[2, 0, 0][t] - k1a* RAFK[t]*S[2, 0, 0][t] + d1a*S_RAFK[2, 0,
0][t]  
S[2, 0, 1] | 0 | (S[2, 0, 1])'[t] == kpon*K[1, 2][t]*S[-1, 0,  1][t] +
kon*K[2, 0][t]*S[2, -1, 1][t] +  kpon*K[3, 1][t]*S[2, 0, -1][t] - k3*S[2, 0,
1][t] - koff*S[2, 0, 1][t] - 2*kpoff*S[2,  0, 1][t] + k1*S_RAFK[2, 0, 0][t]  
S[2, 1, -1] | 0 | (S[2, 1, -1])'[t] == kpon*K[1, 2][t]*S[-1, 1,  -1][t] +
kpon*K[2, 1][t]*S[2, -1, -1][t] -  2*kpoff*S[2, 1, -1][t] - kon*K[3,
0][t]*S[2,  1, -1][t] - kpon*K[3, 1][t]*S[2, 1, -1][t]  + koff*S[2, 1, 0][t] +
kpoff*S[2, 1, 1] [t]  
S[2, 1, 0] | 0 | (S[2, 1, 0])'[t] == kpon*K[1, 2][t]*S[-1, 1,  0][t] +
kpon*K[2, 1][t]*S[2, -1, 0][t] +  kon*K[3, 0][t]*S[2, 1, -1][t] - koff*S[2, 1,
0][t] - 2*kpoff*S[2, 1, 0][t] - k1a*RAFK[t]* S[2, 1, 0][t] + d1a*S_RAFK[2, 1,
0][t]  
S[2, 1, 1] | 0 | (S[2, 1, 1])'[t] == kpon*K[1, 2][t]*S[-1, 1,  1][t] +
kpon*K[2, 1][t]*S[2, -1, 1][t] +  k3*S[2, 0, 1][t] + kpon*K[3, 1][t]*S[2, 1,
-1][t] - k5a*S[2, 1, 1][t] - 3*kpoff*S[2,  1, 1][t] + k1*S_RAFK[2, 1, 0][t]  
S[2, 2, -1] | 0 | (S[2, 2, -1])'[t] == kpon*K[1, 2][t]*S[-1, 2,  -1][t] +
k9a*S[1, 2, -1][t] + kpon*K[2,  2][t]*S[2, -1, -1][t] - 2*kpoff*S[2, 2, -1][
t] - kon*K[3, 0][t]*S[2, 2, -1][t] - kpon*K[ 3, 1][t]*S[2, 2, -1][t] +
koff*S[2, 2, 0][t]  + kpoff*S[2, 2, 1][t]  
S[2, 2, 0] | 0 | (S[2, 2, 0])'[t] == kpon*K[1, 2][t]*S[-1, 2,  0][t] +
k9a*S[1, 2, 0][t] + kpon*K[2,  2][t]*S[2, -1, 0][t] + kon*K[3, 0][t]*S[2,  2,
-1][t] - koff*S[2, 2, 0][t] - 2* kpoff*S[2, 2, 0][t] - k1a*RAFK[t]*S[2, 2,
0][t]  + d1a*S_RAFK[2, 2, 0][t]  
S[2, 2, 1] | 0 | (S[2, 2, 1])'[t] == kpon*K[1, 2][t]*S[-1, 2,  1][t] +
k9a*S[1, 2, 1][t] + kpon*K[2,  2][t]*S[2, -1, 1][t] + k5a*S[2, 1, 1][t]  +
kpon*K[3, 1][t]*S[2, 2, -1][t] - 3*kpoff* S[2, 2, 1][t] + k1*S_RAFK[2, 2,
0][t]  
S_RAFK[-1, -1, 0] | 0 | (S_RAFK[-1, -1, 0])'[t] == k1a*RAFK[t]*S[-1, -1,
0][t] - d1a*S_RAFK[-1, -1, 0][t] - k1* S_RAFK[-1, -1, 0][t]  
S_RAFK[-1, 0, 0] | 0 | (S_RAFK[-1, 0, 0])'[t] == k1a*RAFK[t]*S[-1, 0,  0][t] -
d1a*S_RAFK[-1, 0, 0][t] - k1*S_RAFK[ -1, 0, 0][t]  
S_RAFK[-1, 1, 0] | 0 | (S_RAFK[-1, 1, 0])'[t] == k1a*RAFK[t]*S[-1, 1,  0][t] -
d1a*S_RAFK[-1, 1, 0][t] - k1*S_RAFK[ -1, 1, 0][t]  
S_RAFK[-1, 2, 0] | 0 | (S_RAFK[-1, 2, 0])'[t] == k1a*RAFK[t]*S[-1, 2,  0][t] -
d1a*S_RAFK[-1, 2, 0][t] - k1*S_RAFK[ -1, 2, 0][t]  
S_RAFK[0, -1, 0] | 0 | (S_RAFK[0, -1, 0])'[t] == k1a*RAFK[t]*S[0, -1,  0][t] -
d1a*S_RAFK[0, -1, 0][t] - k1*S_RAFK[ 0, -1, 0][t]  
S_RAFK[0, 0, 0] | 0 | (S_RAFK[0, 0, 0])'[t] == k1a*RAFK[t]*S[0, 0,  0][t] -
d1a*S_RAFK[0, 0, 0][t] - k1*S_RAFK[ 0, 0, 0][t]  
S_RAFK[0, 1, 0] | 0 | (S_RAFK[0, 1, 0])'[t] == k1a*RAFK[t]*S[0, 1,  0][t] -
d1a*S_RAFK[0, 1, 0][t] - k1*S_RAFK[ 0, 1, 0][t]  
S_RAFK[0, 2, 0] | 0 | (S_RAFK[0, 2, 0])'[t] == k1a*RAFK[t]*S[0, 2,  0][t] -
d1a*S_RAFK[0, 2, 0][t] - k1*S_RAFK[ 0, 2, 0][t]  
S_RAFK[1, -1, 0] | 0 | (S_RAFK[1, -1, 0])'[t] == k1a*RAFK[t]*S[1, -1,  0][t] -
d1a*S_RAFK[1, -1, 0][t] - k1*S_RAFK[ 1, -1, 0][t]  
S_RAFK[1, 0, 0] | 0 | (S_RAFK[1, 0, 0])'[t] == k1a*RAFK[t]*S[1, 0,  0][t] -
d1a*S_RAFK[1, 0, 0][t] - k1*S_RAFK[ 1, 0, 0][t]  
S_RAFK[1, 1, 0] | 0 | (S_RAFK[1, 1, 0])'[t] == k1a*RAFK[t]*S[1, 1,  0][t] -
d1a*S_RAFK[1, 1, 0][t] - k1*S_RAFK[ 1, 1, 0][t]  
S_RAFK[1, 2, 0] | 0 | (S_RAFK[1, 2, 0])'[t] == k1a*RAFK[t]*S[1, 2,  0][t] -
d1a*S_RAFK[1, 2, 0][t] - k1*S_RAFK[ 1, 2, 0][t]  
S_RAFK[2, -1, 0] | 0 | (S_RAFK[2, -1, 0])'[t] == k1a*RAFK[t]*S[2, -1,  0][t] -
d1a*S_RAFK[2, -1, 0][t] - k1*S_RAFK[ 2, -1, 0][t]  
S_RAFK[2, 0, 0] | 0 | (S_RAFK[2, 0, 0])'[t] == k1a*RAFK[t]*S[2, 0,  0][t] -
d1a*S_RAFK[2, 0, 0][t] - k1*S_RAFK[ 2, 0, 0][t]  
S_RAFK[2, 1, 0] | 0 | (S_RAFK[2, 1, 0])'[t] == k1a*RAFK[t]*S[2, 1,  0][t] -
d1a*S_RAFK[2, 1, 0][t] - k1*S_RAFK[ 2, 1, 0][t]  
S_RAFK[2, 2, 0] | 0 | (S_RAFK[2, 2, 0])'[t] == k1a*RAFK[t]*S[2, 2,  0][t] -
d1a*S_RAFK[2, 2, 0][t] - k1*S_RAFK[ 2, 2, 0][t]  
  
Generated by Cellerator Version 1.0 update 2.1203 using Mathematica 4.2 for
Mac OS X (June 4, 2002), December 4, 2002 15:06:10, using
(PowerMac,PowerPC,Mac OS X,MacOSX,Darwin)

author=B.E.Shapiro


