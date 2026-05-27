# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: 
RegisterNumber: 
*/
import numpy as np
import sys

# 1. Input configuration
n = int(input("Enter number of unknowns: "))

# Making numpy array of size n x n+1 and initializing it to 0
matrix = np.zeros((n, n + 1))

# Making numpy array of size n and initializing it to 0
x = np.zeros(n)

print("\nEnter Augmented Matrix Coefficients row-wise:")
for i in range(n):
    for j in range(n + 1):
        matrix[i][j] = float(input(f"matrix[{i}][{j}] = "))

# 2. Applying Gaussian Elimination (Forward Elimination)
for i in range(n):
    if matrix[i][i] == 0.0:
        sys.exit("Divide by zero detected! Pivot element is zero.")

    for j in range(i + 1, n):
        ratio = matrix[j][i] / matrix[i][i]

        for k in range(n + 1):
            matrix[j][k] = matrix[j][k] - ratio * matrix[i][k]

# 3. Applying Back Substitution
x[n - 1] = matrix[n - 1][n] / matrix[n - 1][n - 1]

for i in range(n - 2, -1, -1):
    x[i] = matrix[i][n]

    for j in range(i + 1, n):
        x[i] = x[i] - matrix[i][j] * x[j]

    x[i] = x[i] / matrix[i][i]

# 4. Displaying solution
print("\nThe solution is: ")
for i in range(n):
    print(f"X{i} = {x[i]:.2f}")
```

## Output:

The solution is: 
X0 = 1.00
X1 = 3.00
X2 = 5.00



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

