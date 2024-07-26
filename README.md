# Higgs pT

## Install

In a conda environment:
```
pip install -e .
```

## Test locally

```
python -u -W ignore src/run.py --year 2023  --starti 0 --endi 1 --samples VJets --subsamples Zto2Q-4Jets_HT-400to600 --processor ptSkimmer --nano-version v12
```
