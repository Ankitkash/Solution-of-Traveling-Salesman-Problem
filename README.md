# Solution-of-Traveling-Salesman-Problem
## Definition
The Traveling Salesman Problem (TSP) can be defined as follows:
Suppose a salesperson needs to travel from one city to all the other cities exactly once to sell products, and then return to the starting city. The objective is to complete this journey while covering the minimum total distance.
Given `n` cities to visit, the number of possible paths the salesperson must explore is `n!`, and the total number of possible routes can be calculated as:
(n−1)! / 2
This shows how quickly the complexity of the problem grows as the number of cities increases, making it challenging to solve using traditional methods for large `n`.

**Brute Force Method:**
A classical approach that computes all possible permutations of cities and selects the shortest route. While this method guarantees an optimal solution, it becomes computationally expensive as the number of cities increases due to factorial scaling.

**Variational Quantum Eigensolver (VQE) Method:**
A quantum-classical hybrid approach using Qiskit's VQE algorithm. The TSP is represented as a combinatorial optimization problem, where the solution is obtained by minimizing the corresponding Hamiltonian. This method leverages quantum circuits combined with classical optimization to find approximate solutions more efficiently for larger problems.

## How It Works
### Brute Force
The brute force method iterates over all possible permutations of city paths, calculating and comparing the total distance for each path. It then selects the shortest one. Although this method guarantees the optimal solution, it becomes computationally expensive as the number of cities increases.

### VQE (Variational Quantum Eigensolver)
In simple terms, the VQE algorithm finds the lowest eigenvalue and its corresponding eigenvector for a given Hamiltonian. It operates based on the **variational principle**, which states that the expectation value of the Hamiltonian (H) in any quantum state (|ψ⟩) is greater than or equal to the lowest eigenvalue (λmin):

λmin ≤ ⟨ψ|H|ψ⟩

The VQE algorithm has two main parts:

1. **Quantum Part**:  
   - Runs quantum circuits to prepare a quantum state.
   - Measures the expectation value of the Hamiltonian for that quantum state.

2. **Classical Part**:  
   - A classical optimizer adjusts the parameters of the quantum circuit to minimize the expectation value of the Hamiltonian.
   - The goal is to approximate the lowest eigenvalue, which corresponds to the solution of the optimization problem (the shortest path in TSP).
  
## Limitations and Challenges
Simulating quantum circuits on classical computers has proven to be computationally expensive and time-consuming due to the exponential growth of quantum states with the number of qubits. Specifically, if we have `n` cities, the number of qubits required is `n^2`, and the number of quantum states grows as `2^(n^2)`, which becomes very large for even modest values of `n`.
These challenges highlight the need for further research and optimization strategies to overcome quantum resource constraints and improve the efficiency of quantum algorithms. Despite these limitations, the findings of this research contribute significantly to advancing our understanding of quantum computing and its potential applications in solving complex optimization problems.
