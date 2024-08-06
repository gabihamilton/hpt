# Higgs pT

## Install

First, create a virtual environment (`micromamba` is recommended):

```bash
# Download the micromamba setup script (change if needed for your machine https://mamba.readthedocs.io/en/latest/installation/micromamba-installation.html)
# Install: (the micromamba directory can end up taking O(1-10GB) so make sure the directory you're using allows that quota)
"${SHELL}" <(curl -L micro.mamba.pm/install.sh)
# You may need to restart your shell
micromamba create -n hpt-env python=3.10 -c conda-forge
micromamba activate hpt-env
```

### Installing package

**Remember to install this in your mamba environment**.

```bash
# Clone the repository
git clone https://github.com/cmantill/hpt.git
cd hpt
# Perform an editable installation
pip install -e .
```
To install the requirements
```bash
pip install -r requirements.txt
pip install xrootd
python3 -m pip install setuptools==59.5.0
```


## Run locally

e.g. for a test
```
python -u -W ignore src/run.py --year 2023  --starti 0 --endi 1 --samples VJets --subsamples Zto2Q-4Jets_HT-400to600 --processor ptSkimmer --nano-version v12
```

## Submit jobs

e.g. for HH
```
python src/condor/submit.py --processor ptSkimmer --tag 24Jul26 --files-per-job 20 --submit --samples HH --nano-version v12 --git-branch main --year 2023
```

