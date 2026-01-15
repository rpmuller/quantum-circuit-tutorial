# Quantum Circuit Tutorial Project

## Project Overview

A comprehensive series of Jupyter notebook tutorials demonstrating quantum computing algorithms and how they achieve quantum speedups. All circuits are constructed and implemented in Qiskit (Python) and run on quantum simulators.

**Environment Management**: This project uses `uv` for Python dependency management.

**Repository**: https://github.com/rpmuller/quantum-circuit-tutorial

## Current Status

### Completed Notebooks

1. **deutsch.ipynb** - Deutsch's Algorithm
   - The first quantum algorithm to demonstrate speedup (2x)
   - Problem: Determine if 1-bit function is constant or balanced
   - Classical: 2 queries | Quantum: 1 query
   - Covers: quantum parallelism, phase kickback, superposition, interference
   - Implements all 4 possible oracles with visualizations

2. **deutsch-jozsa.ipynb** - Deutsch-Jozsa Algorithm
   - Exponential quantum speedup
   - Problem: Determine if n-bit function is constant or balanced
   - Classical: 2^(n-1) + 1 queries | Quantum: 1 query
   - Shows speedup from 3x (n=2) to 524,289x (n=20)
   - Includes examples for n=2, n=4, and n=8
   - Flexible oracles: constant, alternating, parity, random patterns

3. **bernstein-vazirani.ipynb** - Bernstein-Vazirani Algorithm
   - Linear quantum speedup for finding hidden bit strings
   - Problem: Find hidden n-bit string s where f(x) = s·x (mod 2)
   - Classical: n queries | Quantum: 1 query
   - Shows speedup from 4x (n=4) to 64x (n=64)
   - Includes examples for n=3, n=4, and n=8
   - Demonstrates phase-based information encoding and extraction
   - Foundation for Simon's and Shor's algorithms

### Dependencies

All installed via `uv`:
- `qiskit` - Quantum circuit framework
- `qiskit-aer` - Quantum circuit simulator
- `matplotlib` - Visualizations and plotting
- `ipykernel` - Jupyter notebook support in VS Code
- `pylatexenc` - LaTeX rendering for circuit diagrams

## Notebook Style Guide

Each notebook should follow this comprehensive structure:

### Content Structure
1. **Introduction**: Clear problem statement and context
2. **Classical vs Quantum Comparison**: Complexity analysis showing the speedup
3. **Theory**: Mathematical foundations and why the algorithm works
4. **Oracle Implementations**: All relevant test cases
5. **Complete Qiskit Implementation**: Working code with proper documentation
6. **Multiple Examples**: Start small (n=2,3,4) and scale up to demonstrate speedup
7. **Visualizations**:
   - Circuit diagrams using `circuit.draw('mpl')`
   - Result histograms using `plot_histogram()`
   - Speedup comparison plots
8. **Mathematical Walkthrough**: Step-by-step quantum state evolution
9. **Key Insights**: What makes the quantum speedup possible
10. **Conclusion**: Summary and connections to other algorithms

### Style Guidelines
- **Comprehensive**: Include theory, math, multiple examples, and visualizations
- **Pedagogical**: Explain concepts clearly, build on previous notebooks
- **Simulation Focus**: Use Qiskit's AerSimulator, no real hardware considerations
- **Executable**: All code cells should run successfully
- **Self-contained**: Each notebook should be understandable independently
- **Cross-references**: Link back to concepts from previous notebooks where relevant

### Code Conventions
- Use descriptive function names and docstrings
- Include comments explaining quantum operations
- Show circuit diagrams for oracles and complete algorithms
- Run circuits with 1000 shots for statistical validation
- Use barriers in circuits to clearly show algorithm phases

## Planned Notebooks (In Priority Order)

1. **Simon's Algorithm**
   - Finding hidden XOR patterns (period finding)
   - Exponential speedup over classical
   - Important precursor to Shor's algorithm

2. **Grover's Algorithm**
   - Quantum search/unstructured database search
   - Quadratic speedup: O(N) → O(√N)
   - One of the most practically useful quantum algorithms

3. **Quantum Fourier Transform (QFT)**
   - Foundation for many quantum algorithms
   - Exponentially faster than classical FFT
   - Required for Shor's algorithm and phase estimation
   - Can lead to Shor's factoring algorithm as advanced topic

## Development Workflow

1. Create notebook with comprehensive content following style guide
2. Test all code cells execute successfully
3. Verify visualizations render properly (may need kernel restart after installing packages)
4. Commit notebook with descriptive commit message
5. Update README.md with notebook description and links
6. Push to GitHub

## Important Notes

- **Kernel Restarts**: After installing new packages with `uv add`, restart Jupyter kernel to pick up changes
- **Dependencies**: Add any new visualization or quantum libraries to `pyproject.toml` via `uv add`
- **File Naming**: Use lowercase with hyphens (e.g., `deutsch-jozsa.ipynb`)
- **Commits**: Include "Co-Authored-By: Claude Sonnet 4.5 <noreply@anthropic.com>"
- **Testing**: Run all cells top-to-bottom before committing

## Resources for Algorithm Development

- Qiskit Textbook: https://qiskit.org/textbook/
- Nielsen & Chuang: Quantum Computation and Quantum Information
- Qiskit Documentation: https://qiskit.org/documentation/

## Project Goals

- Make quantum computing concepts accessible through hands-on learning
- Demonstrate both theoretical foundations and practical implementations
- Show clear progression from simple (Deutsch) to complex (QFT/Shor) algorithms
- Emphasize understanding of quantum speedup mechanisms
- Provide working code that students can modify and experiment with 