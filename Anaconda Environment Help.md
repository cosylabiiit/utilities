- Create Anaconda environment: 
```bash 
conda create -n {name_of_env} python={python_version}
```
- Activate environment:  
```bash 
conda activate {name_of_env}
```
- Installing packages:
  1. Make sure you activate your environment first.
  2. Use pip/conda package manager to install.
- Installing jupyter notebook kernel:  
```bash
pip install ipykernel  
python -m ipykernel install --user {name_of_kernel}
```

