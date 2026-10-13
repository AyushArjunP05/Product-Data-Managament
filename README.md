# Product-Data-Managament

Solving Linear Systems in Python Using Gaussian Elimination :

Project Overview :
This project demonstrates how to solve a system of linear equations using Gaussian Elimination in Python. A manufacturing production-planning scenario is used to show how linear algebra can help determine production quantities when machine-hour availability is limited.
The implementation uses NumPy for matrix representation and numerical operations, while the Gaussian Elimination algorithm is implemented step by step using forward elimination and back substitution.

Problem Statement :
A manufacturing facility produces three products — A, B, and C — using three machines. Each machine has a limited number of available hours. The goal is to determine how many batches of each product can be produced while satisfying all machine-hour constraints.

Let:
- x = number of batches of Product A
- y = number of batches of Product B
- z = number of batches of Product C
The machine-hour constraints are:
- 3x + 2y + z = 19
- 2x + 3y + z = 22
- x + y + 2z = 13

Mathematical Formulation :
The system can be represented as AX = b, where
A = [[3, 2, 1],
     [2, 3, 1],
     [1, 1, 2]]

X = [x, y, z]
b = [19, 22, 13]
The solution is:
- Product A (x): 2 batches
- Product B (y): 5 batches
- Product C (z): 3 batches
  
Method :
Gaussian Elimination has two main stages:
1. Forward elimination: Use row operations to convert the augmented matrix into upper-triangular form.
2. Back substitution: Solve the resulting equations from the last row to the first.
The program also verifies the result by calculating the residual:
r = AX - b
For this example, the residual is [0, 0, 0], so all three equations are satisfied (up to floating-point precision).
Requirements
- Python 3
- NumPy

Run the Project :
Option 1: Google Colab
1. Open Google Colab.
2. Create a new notebook or upload your project notebook.
3. Run the cells in order.
NumPy is commonly available in Google Colab. If needed, install it in a notebook cell:
!pip install numpy
Option 2: Run locally
1. Install Python 3 from python.org.
2. Install NumPy:
   python -m pip install numpy
3. Save the notebook code in a Python file (for example, gaussian_elimination.py) or run it in a Jupyter Notebook.
4. Execute the Python file:
   python gaussian_elimination.py
   
Verification :
The project checks the computed solution using matrix multiplication:
calculated_values = A @ solution
residual = A @ solution - b
It can also compare the custom implementation with NumPy's built-in solver:
numpy_solution = np.linalg.solve(A, b)
The two solutions should agree, allowing for minor floating-point differences.

Limitations :
- The basic implementation assumes a nonzero pivot at each elimination step.
- It does not automatically swap rows when a zero pivot occurs.
- For more robust numerical behavior, partial pivoting and checks for singular or inconsistent systems should be added.

Project Structure
A simple repository structure could be:
solving-linear-systems/
├── README.md
└── gaussian_elimination.py

Learning Outcomes
- Represent a system of linear equations using matrices.
- Understand augmented matrices and elementary row operations.
- Implement forward elimination and back substitution.
- Verify a solution using residuals and an independent numerical solver.
- Apply linear algebra to a practical production-planning example
