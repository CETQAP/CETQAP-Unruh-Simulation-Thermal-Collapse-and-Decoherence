readme_content = """
# Unruh Effect Quantum Simulation

This repository contains a Qiskit-based quantum simulation of the **Unruh Effect**, a relativistic quantum phenomenon that predicts thermal radiation observed by an accelerating observer in a vacuum.

The simulation:
- Applies Bogoliubov transformations via parameterized quantum gates  
- Measures quantum purity, entropy, and Z-expectation  
- Computes fidelity with the vacuum state  
- Compares the output with thermal distribution  
- Saves statevector and Q-sphere visualizations  
- Runs on either IBM Quantum hardware or local Aer simulator  

---

## Features

- IBM Quantum Runtime + Hardware Support (default: `ibm_brisbane`)  
- Dynamic Squeezing Parameter (`r`)  
- Visualizations: Circuit Diagram, Statevector City, Q-Sphere  
- Reduced Density Matrix Analysis (partial trace)  
- Thermal Distribution Matching  
- Fidelity with Custom Target State  
- Robust error handling & fallback to AerSimulator  

---

## Directory Structure

.
├── unruh_simulation_results/
│ ├── circuit_diagram_<timestamp>.png
│ ├── statevector_plot_<timestamp>.png
│ ├── qsphere_plot_<timestamp>.png
│ └── results_<timestamp>.json
├── unruh_simulation.py
└── README.md


---

## How to Run

### 1. Prerequisites

- Python 3.8+
- IBM Quantum account ([Sign up here](https://quantum.ibm.com))
- Install required libraries:


pip install qiskit qiskit_ibm_runtime matplotlib numpy
pip install seaborn pylatexenc
python unruh_simulation.py
You will be prompted to:

Enter your IBM Quantum API Key

Optionally enter a squeezing parameter r (between 0 and ~2)

Optionally enter a target state (e.g., 00, 11) for fidelity comparison

Output Metrics
The simulation outputs:

Purity: Degree of mixedness of the reduced state

Von Neumann Entropy: Entanglement indicator

Z-Expectation Value: From partial trace over one qubit

Fidelity vs Vacuum: Similarity with target state

Thermal Match: Whether measured probabilities match expected thermal population

Counts: Raw and normalized qubit measurement data

Example Output
{
  "job_id": "ck4qx2w8q6z1v018f1sg",
  "counts": {"0": "65%", "1": "35%"},
  "expectation_Z": -0.67,
  "purity": 0.49,
  "entropy": 0.71,
  "fidelity_vs_vacuum": 0.58,
  "thermal_distribution_match": true,
  "squeezed_entangled_counts": {"00": "38%", "11": "32%"},
  "entanglement_entropy": 0.71,
  "raw_counts": {"00": 284, "11": 242, "01": 130, "10": 94}
}

Scientific Background
The Unruh effect predicts that an accelerating observer will perceive the Minkowski vacuum as a thermal bath. This simulation applies the Bogoliubov transformation using gate-based quantum computing to emulate this effect under simplified assumptions (e.g., squeezing parameters).

Author
Tooba Abdul Razzaq
Student Researcher, CETQAC (The Centre of Excellence for Technology Quantum and AI Canada) 
Extended Dr. Zuhair Ahmed's Unruh Simulation Model
