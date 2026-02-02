# Scalable Quantum Tomography Pipelines — Assignment 3

## Overview

This project explores scalable surrogate approaches for quantum state tomography.  
The goal is to study how tomography-related computations behave as the number of qubits increases.

We implement:
- Model serialization with pickle
- An extendable n-qubit surrogate model
- Scalability experiments
- Ablation studies
- Visualization of fidelity and runtime trends

---

## Project Structure

```

Assignment_3/
│
├── Assignment_3.ipynb
├── scalability_results.csv
│
├── models/
│ ├── model_qst_1.pkl
│ └── README.md
│
└── README.md

```
---

## Model Description

The surrogate model represents a quantum state as a normalized complex vector of dimension:

```
2^n
```

where `n` is the number of qubits.

Fidelity is computed between predicted and target states to evaluate performance.

---

## Serialization

Models are saved using Python pickle.

### Example

```python
import pickle

with open("models/model_qst_1.pkl", "rb") as f:
    model = pickle.load(f)
```

### Naming Convention

```
model_<track>_<nqubits>.pkl
```

Example:

```
model_qst_1.pkl
```

---

## Scalability Study

We measure:

- Average fidelity  
- Fidelity variance  
- Runtime  

Results show decreasing fidelity as qubit count increases due to exponential growth of Hilbert space.

---

## Ablation Study

We varied model depth (layers) and observed:

- Small variation in fidelity  
- No major improvement without training  

This indicates that optimization is necessary for high-quality tomography.

---

## Limitations

- Random (untrained) parameters  
- No noise modeling  
- Small qubit counts tested  
- Simplified surrogate model  

---

## Future Work

Possible extensions:

- Training-based tomography  
- Classical shadow tomography  
- Noise-aware simulations  
- Experiments on real quantum hardware  
- Larger qubit systems  

---

## Requirements

Python 3.x

Libraries:

- numpy  
- pandas  
- matplotlib  
- pickle (standard library)  

---