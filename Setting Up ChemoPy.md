
1. Install Anaconda (https://www.anaconda.com/distribution/)
2. Create and activate Python2.7 environment:
```bash
conda create -n python27 python=2.7
conda activate python27
```
3. Install OpenBabel and RDKit
```bash
conda install -c openbabel openbabel
conda install -c rdkit rdkit
```
4. Install ChemoPy
```bash
pip install -e git+https://github.com/cosylabiiit/chemopy
```
5. Generate all ChemoPy properties
```python
from pychem.pychem import Chem, constitution, connectivity, kappa, bcut,\
    moran, geary, molproperty, charge, moe, estate, basak
    
def get_chemopy_props(smiles):
    mol = Chem.MolFromSmiles(smiles)
    props = {}
    try:
        props.update(constitution.GetConstitutional(mol))
        props.update(connectivity.GetConnectivity(mol))
        props.update(kappa.GetKappa(mol))
        props.update(bcut.GetBurden(mol))
        props.update(estate.GetEstate(mol))
        props.update(basak.Getbasak(mol))
        props.update(moran.GetMoranAuto(mol))
        props.update(geary.GetGearyAuto(mol))
        props.update(molproperty.GetMolecularProperty(mol))
        props.update(charge.GetCharge(mol))
        props.update(moe.GetMOE(mol))

    except:
        pass

    return props
```


