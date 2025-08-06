# Shipment Rerouting: Classical vs Quantum Algorithms

This repository contains code for experiments comparing classical and quantum approaches to the shipment rerouting problem on real-life transportation networks.

📄 **Paper Reference**: These experiments were conducted as part of a study comparing classical optimization algorithms with quantum algorithms using real-world data.  
📊 **Data Source**: [Transportation Networks GitHub Repository](https://github.com/bstabler/TransportationNetworks)

---

## 🧪 Experimental Setup

### Networks Used
Experiments are conducted across the following five transportation networks:

| Network              | # Nodes | # Edges |
|----------------------|---------|---------|
| Eastern Massachusetts| 74      | 258     |
| Anaheim              | 416     | 914     |
| Chicago              | 933     | 2950    |
| Winnipeg             | 1052    | 2836    |
| Barcelona            | 1020    | 2552    |

### Input Generation

- Truck runs are randomly generated from each network.
- Candidate routes are computed via depth-first search from each shipment’s source to destination.
- Each shipment is limited to **five candidate routes** to manage complexity.

### Input Sizes

- **Small-scale tests**: 30, 50, 80, 100 runs
- **Large-scale tests**: 32, 64, 128, 256, 512, 1024 runs
  - Large tests require **IBM CPLEX Optimization Studio**.

---

## ⚙️ Requirements

### Classical Algorithms

- Python 3.8+
- Dependencies (see `requirements.txt`):
  - `numpy`
  - `networkx`
  - `matplotlib`
  - `cplex` (via IBM CPLEX)
  - `pandas`

Tested on:
- CPU: Intel Core i7-1260P (12th Gen)
- RAM: 16 GB

### Quantum Algorithms

- Uses D-Wave’s **Leap Hybrid Solver** via `PyQUBO` and `Ocean SDK`

Dependencies:
- `dwave-ocean-sdk`
- `pyqubo`
- `dimod`

### Installation Notes

For CPLEX:
- Download and install [IBM CPLEX Optimization Studio](https://www.ibm.com/products/ilog-cplex-optimization-studio)
- Ensure Python API for CPLEX is installed (`cplex` module)

For D-Wave:
- Sign up for a [D-Wave Leap account](https://cloud.dwavesys.com/leap/)
- Set up API token as per Ocean documentation

---
