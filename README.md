# Energy Minimization Using Conjugate-Gradient Method

## Overview
This project implements an energy minimization algorithm using the **conjugate-gradient** method to find stable configurations of **Lennard-Jones particles**. The goal is to identify energetically favorable clusters by iteratively optimizing randomly distributed particles in a 3D space.

## Problem Statement
Clusters of atoms or molecules can form stable structures based on their **energetic interactions**. Some cluster sizes, known as **magic numbers**, result in particularly stable configurations. To find such stable clusters, we:

1. Model interactions using the **dimensionless Lennard-Jones potential**.
2. Start with a **random configuration** of particles.
3. Apply an **energy minimization algorithm** to locate a stable low-energy structure.
4. Repeat the process multiple times to explore different configurations.

## Methodology
The algorithm follows these main steps:

1. **Initialize Positions:** Randomly distribute `N` atoms within a cubic box of size `L`, ensuring the center is at the origin.
2. **Calculate Energy:** Compute the potential energy using the Lennard-Jones potential.
3. **Calculate Forces:** Derive the force acting on each particle as the gradient of the energy function.
4. **Perform Line Search:** Optimize positions along the force directions while maintaining constraints.
5. **Conjugate-Gradient Minimization:** Perform multiple iterations (M = 10,000) from different initial configurations to find the global energy minimum.

## Implementation Details
- **SciPy and NumPy** are **not used** for the actual optimization steps but may be utilized for validation.
- The line search and conjugate-gradient algorithms are implemented from scratch.
- The stopping criteria include:
  - Line search tolerance: `LStol = 10⁻⁸`
  - Energy convergence tolerance: `ECtol = 10⁻¹⁰`
  - Maximum iterations for both methods: `100,000`

## Usage
To run the script:
```bash
python energy_minimization.ipynb
```

* See task.pdf for more detailed explanation of the task
* See results.pdf for detailed results