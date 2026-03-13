# Quantum Computing Simulations

A collection of research-oriented Jupyter notebooks exploring quantum computing algorithms and protocols using [Qiskit](https://qiskit.org/).

## Notebooks

| Notebook | Topics | Qubits | Level |
|----------|--------|--------|-------|
| **[01 — Quantum Computing Fundamentals](quantum_computing_simulations.ipynb)** | Single-qubit gates, Bell states, teleportation, Deutsch–Jozsa, Grover's search, noise simulation | 1–3 | Introductory |
| **[02 — QFT & Shor's Algorithm](qft_shors_algorithm.ipynb)** | Quantum Fourier Transform, phase estimation, modular exponentiation, Shor's factoring (N=15, 21, 33, 35) | 4–14 | Advanced |
| **[03 — Variational Quantum Eigensolver](variational_quantum_eigensolver.ipynb)** | VQE framework, Pauli Hamiltonians, ansatz design, H₂ & LiH ground states, noise-aware VQE, barren plateaus | 2–6 | Advanced |

## Getting Started

### Prerequisites

- Python ≥ 3.9
- Jupyter Notebook or JupyterLab

### Installation

```bash
git clone https://github.com/<your-username>/quantum-computing-simulations.git
cd quantum-computing-simulations
pip install -r requirements.txt
jupyter lab
```

### Quick Verification

```python
from qiskit import QuantumCircuit
from qiskit_aer import AerSimulator

qc = QuantumCircuit(2, 2)
qc.h(0)
qc.cx(0, 1)
qc.measure([0, 1], [0, 1])

result = AerSimulator().run(qc, shots=1024).result()
print(result.get_counts())
# Expected: {'00': ~512, '11': ~512}
```

## What's Covered

### Fundamentals
- Bloch sphere visualisation
- Quantum entanglement (all four Bell states)
- Quantum teleportation protocol
- Deutsch–Jozsa algorithm (exponential speedup over classical)
- Grover's search with amplitude amplification analysis
- Depolarising noise models and fidelity degradation

### QFT & Shor's Algorithm
- QFT circuit construction and verification against analytic DFT matrix
- Approximate QFT with Coppersmith truncation
- Quantum phase estimation (QPE) with precision analysis
- Full Shor's algorithm with continued-fraction post-processing
- Factoring N = 15, 21, 33, 35
- Circuit resource scaling analysis

### Variational Quantum Eigensolver
- Hamiltonian encoding via Pauli decomposition
- Hardware-efficient ansätze (RealAmplitudes, EfficientSU2)
- Exact vs. shot-based expectation value estimation
- H₂ potential energy surface (14 bond lengths)
- Optimiser comparison (COBYLA, L-BFGS-B, Nelder-Mead, Powell)
- Noise-aware VQE under shot noise and gate errors
- Barren plateau demonstration (gradient variance scaling)
- LiH ground state (6-qubit benchmark)

## Tech Stack

- **Qiskit 2.x** — circuit construction, transpilation, quantum info
- **Qiskit Aer** — high-performance statevector and shot-based simulation
- **SciPy** — classical optimisation (COBYLA, L-BFGS-B, etc.)
- **Matplotlib** — visualisation

## References

- Nielsen, M. A. & Chuang, I. L. (2010). *Quantum Computation and Quantum Information*. Cambridge University Press.
- Shor, P. W. (1994). "Algorithms for quantum computation: discrete logarithms and factoring." *FOCS*.
- Peruzzo, A. et al. (2014). "A variational eigenvalue solver on a photonic quantum processor." *Nature Communications*.
- McClean, J. R. et al. (2018). "Barren plateaus in quantum neural network training landscapes." *Nature Communications*.
- Gidney, C. & Ekerå, M. (2021). "How to factor 2048 bit RSA integers in 8 hours using 20 million noisy qubits." *Quantum*.

## License

MIT — see [LICENSE](LICENSE).
