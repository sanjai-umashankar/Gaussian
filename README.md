# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the number of unknowns n and the augmented matrix entries from user input.
2. Reshape the input into an n\times (n+1) augmented matrix A.
3. For each pivot row i, eliminate entries below the pivot by subtracting a factor times the pivot row.
4. Initialize solution vector x with zeros.
5. Perform back substitution: compute each variable from the last row upwards using the formula in the code.
6. Print the solution values of all variables in formatted output. 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: SANJAI U 
RegisterNumber: 212224240145
*/
import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"
import numpy as np
n = int(input())
A = np.zeros((n, n + 1))
for i in range(n):
    for j in range(n + 1):
        A[i][j] = float(input())
for i in range(n):
    for j in range(i + 1, n):
        ratio = A[j][i] / A[i][i]
        for k in range(n + 1):
            A[j][k] = A[j][k] - ratio * A[i][k]
X = np.zeros(n)
X[n - 1] = A[n - 1][n] / A[n - 1][n - 1]
for i in range(n - 2, -1, -1):
    s = 0
    for j in range(i + 1, n):
        s = s + A[i][j] * X[j]
    X[i] = (A[i][n] - s) / A[i][i]
for i in range(n):
    print(f"X{i} = {X[i]:.2f}", end=" ")

```

## Output:

<img width="1481" height="982" alt="image" src="https://github.com/user-attachments/assets/a2b91854-903a-4d04-a43b-9eb7efc6c614" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

