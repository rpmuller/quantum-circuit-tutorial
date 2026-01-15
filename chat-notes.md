# Quantum Algorithms: From Foundational Oracles to Shor’s

This summary covers the progression of quantum complexity, highlighting how each algorithm builds upon its predecessor to demonstrate "quantum advantage."

---

## 1. Deutsch-Jozsa Algorithm
The first to prove that a quantum computer can solve a "black-box" problem faster than any classical machine.

* **Problem:** Is a function $f: \{0,1\}^n \to \{0,1\}$ **constant** or **balanced**?
* **Classical:** Needs $2^{n-1} + 1$ queries for $100\%$ certainty.
* **Quantum:** Needs only **1 query**.
* **Significance:** Introduced **Quantum Parallelism**—using superposition to evaluate all inputs at once.

---

## 2. Bernstein-Vazirani Algorithm
A refinement of Deutsch-Jozsa that finds a hidden string rather than a binary property.

* **Problem:** Find a hidden bitstring $s$ where $f(x) = s \cdot x \pmod 2$.
* **Speedup:** * **Classical:** $n$ queries.
    * **Quantum:** **1 query**.
* **Applications:** Used in **Quantum Error Correction** (identifying bit-flips) and specific cryptographic "Shift" problems.



---

## 3. Simon’s Algorithm
The conceptual "bridge" to Shor’s. It proves that quantum computers can find the period of a function exponentially faster than classical computers.

* **Problem:** Find a hidden period $s$ such that $f(x) = f(y) \iff y = x \oplus s$.
* **Speedup:**
    * **Classical:** $O(2^{n/2})$.
    * **Quantum:** $O(n^2)$.
* **The Shor Connection:** Shor adapted this "period-finding" engine to work with modular exponentiation instead of XOR.



---

## 4. Shor’s Algorithm
The algorithm that makes quantum computing a cryptographic reality by factoring large integers $N$.

* **The Logic:** It converts factoring into a period-finding problem for $f(x) = a^x \pmod N$.
* **Period Finding:** Uses the **Quantum Fourier Transform (QFT)** to find the period $r$.
* **Small $N$ Optimizations:** As Craig Gidney noted, factoring $N=15$ is much easier than $N=21$ because the modular exponentiation $2^x \pmod{15}$ has a period of $4$, and the specific bit-patterns allow for massive gate cancellations during compilation.



---

## Martin Roetteler’s Research (Microsoft)
Martin Roetteler is a key figure in optimizing these algorithms for real hardware. Key areas of his work include:

* **Resource Estimation:** Developing precise counts for the number of qubits and T-gates (the "expensive" gates) needed for RSA and Elliptic Curve cryptography.
* **Modular Arithmetic:** Optimizing the "circuits-within-circuits" used for modular multiplication.
* **Key Paper:** *"Quantum resource estimates for computing elliptic curve discrete logarithms"* (focuses on ECDL, the foundation of modern mobile encryption).

---

## Implementation & Resource Tools (Qiskit)

To implement these or estimate resources, you can use these Python/Qiskit tools:

### 1. Shor’s Implementation
In the latest `qiskit_algorithms` library:
```python
from qiskit_algorithms import Shor
# Note: Requires a quantum instance/backend to run
```
