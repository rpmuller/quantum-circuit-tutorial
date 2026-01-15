# Quantum Circuit Tutorials

A series of interactive Jupyter notebooks demonstrating quantum computing algorithms and how they achieve quantum speedups. These tutorials use [Qiskit](https://qiskit.org/) to construct and simulate quantum circuits in Python.

## Overview

This repository provides hands-on tutorials exploring fundamental quantum algorithms, explaining both the theoretical foundations and practical implementations. Each notebook includes:

- Theoretical background and mathematical derivations
- Working Qiskit circuit implementations
- Visualizations of quantum circuits and results
- Analysis of quantum speedup compared to classical algorithms

## Notebooks

### 1. [Deutsch's Algorithm](deutsch.ipynb)

**The first quantum speedup**

Learn about the algorithm that started it all - the first to demonstrate that quantum computers can outperform classical computers.

- **Problem**: Determine if a function f: {0,1} → {0,1} is constant or balanced
- **Classical complexity**: 2 queries required
- **Quantum complexity**: 1 query (2x speedup)
- **Key concepts**:
  - Quantum parallelism
  - Phase kickback
  - Quantum interference
  - Superposition

**What you'll learn**: How quantum computers can evaluate multiple inputs simultaneously and use interference to extract global properties of functions.

---

### 2. [Deutsch-Jozsa Algorithm](deutsch-jozsa.ipynb)

**Exponential quantum speedup**

Building on Deutsch's algorithm, this tutorial shows how quantum algorithms can achieve exponential speedups by generalizing to n qubits.

- **Problem**: Determine if an n-bit function is constant or balanced
- **Classical complexity**: Up to 2^(n-1) + 1 queries
- **Quantum complexity**: 1 query (exponential speedup!)
- **Key concepts**:
  - Quantum parallelism at scale
  - Global vs local information
  - Constructive and destructive interference
  - Promise problems

**Speedup examples**:
- n=4: 9x speedup
- n=8: 129x speedup
- n=20: 524,289x speedup

**What you'll learn**: How quantum interference enables extracting global properties without learning individual input-output pairs, demonstrating the power of quantum computing.

---

## Getting Started

### Prerequisites

This project uses [uv](https://github.com/astral-sh/uv) for Python environment management.

### Installation

1. Clone the repository:
```bash
git clone https://github.com/rpmuller/quantum-circuit-tutorial.git
cd quantum-circuit-tutorial
```

2. Install dependencies with uv:
```bash
uv sync
```

### Running the Notebooks

Open the notebooks in VS Code, Jupyter Lab, or your preferred notebook environment:

```bash
jupyter lab
```

Make sure to select the Python interpreter from the uv virtual environment (`.venv`).

## Dependencies

- **qiskit**: Quantum computing framework
- **qiskit-aer**: High-performance quantum circuit simulator
- **matplotlib**: Visualization and plotting
- **ipykernel**: Jupyter notebook support
- **pylatexenc**: Enhanced LaTeX rendering for circuit diagrams

## Learning Path

We recommend following the notebooks in order:

1. Start with **Deutsch's Algorithm** to understand the basic principles
2. Progress to **Deutsch-Jozsa** to see how these principles scale exponentially

## Contributing

Contributions are welcome! Feel free to:
- Report issues or bugs
- Suggest new quantum algorithms to cover
- Improve explanations or add visualizations
- Fix typos or errors

## License

This project is open source and available for educational purposes.

## Resources

- [Qiskit Documentation](https://qiskit.org/documentation/)
- [Qiskit Textbook](https://qiskit.org/textbook/)
- [Nielsen & Chuang: Quantum Computation and Quantum Information](http://mmrc.amss.cas.cn/tlb/201702/W020170224608149940643.pdf)

## Acknowledgments

These tutorials were created to make quantum computing concepts accessible through interactive, hands-on learning with real quantum circuit simulations.
