# Two-Phase Simplex and Gomory Cutting Plane Algorithm Implementation

## Description

This project implements the **Two-Phase Simplex Method** and **Gomory Cutting Plane Algorithm** to solve linear programming and integer programming problems. The solution uses Python and NumPy to efficiently handle tableau manipulations, pivoting, and iterative optimization. 

### Key Features:
- **Two-Phase Simplex Method**: Solves linear programming problems by first finding a feasible solution (Phase I) and then optimizing (Phase II).
- **Gomory Cutting Plane Algorithm**: Adds cutting-plane constraints to enforce integer solutions for problems where fractional solutions exist.
- Dual simplex for efficient tableau updates during integer constraint handling.

---

## File Structure

- **`main.py`**: Main script containing function definitions and the implementation of algorithms.
- **`input.txt`**: Example input file with problem definitions.

---

## Input Format

The program reads input from a file in the following format:

1. First line: Two integers `n` and `m` (number of variables and constraints).
2. Second line: `m` integers for the `b` vector (right-hand side values).
3. Third line: `n` integers for the `c` vector (objective function coefficients).
4. Next `m` lines: Coefficients of the constraint matrix `A`.

### Example:
    3 3
    2 3 5
    4 6 8
    1 0 1
    0 1 2
    3 1 4

---

## Usage

### Running the Two-Phase Simplex Method:

To find an optimal solution for a linear programming problem:
- 	Define the input problem in input.txt.
-	Call phase_2_simplex(A, b, c, n, m):
	-	A: Constraint matrix.
	-	b: RHS values.
	-	c: Objective function coefficients.
	-	n: Number of variables.
	-	m: Number of constraints.
-	Outputs the optimal solution and tableau.

### Running the Gomory Cutting Plane Algorithm:

To handle integer programming:
-	Use the Gomory algorithm to generate cutting-plane constraints:
	-	gomory_tableau(tableau, n)
-	Use dual simplex for optimization after adding the constraints:
	-	dual_simplex(tableau, basis).

---

## Functions Overview

### Two-Phase Simplex Method:

-	read_file(filename): Reads input and parses the problem definition.
-	convert_std(A, b, c, n, m): Converts the problem into standard form.
-	simplex_method(table, basis): Executes the simplex algorithm.
-	phase_2_simplex(A, b, c, n, m): Combines all steps to execute the two-phase simplex method.

### Gomory Cutting Plane:

-	gomory_constraint(tableau): Identifies fractional solutions for constraints.
-	gomory_tableau(tableau, n): Adds Gomory constraints to enforce integer solutions.
-	dual_simplex(tableau, basis): Optimizes using the dual simplex method.

--- 

## Limitations

-	Only handles LPs in standard form.
-	Assumes that the input problem is well-defined and feasible.
-	For large-scale problems, optimization techniques like sparsity handling may be needed.

---
## Authors

This project was implemented as part of an academic assignment on advanced optimization techniques.
- Ashi Veerman 2021MT10241
- Shreya Gupta 2021MT10906