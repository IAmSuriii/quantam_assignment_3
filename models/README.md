# Model Checkpoints

This folder contains serialized models saved using pickle.

## How to Load

```python
import pickle

with open("models/model_qst_1.pkl", "rb") as f:
    model = pickle.load(f)
```

## Naming Convention

model_<track>_<nqubits>.pkl

Example:
model_qst_1.pkl
