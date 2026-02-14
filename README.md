# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start the program and read the number of unknowns (n). Form the augmented matrix of size n × (n+1).
2. Perform forward elimination:
   For each pivot element, eliminate the elements below it by using the row operation
   Rj = Rj - (ratio × Ri), where ratio = a[j][i] / a[i][i].
3. Perform back substitution:
   Compute the last variable first, then substitute it back into the previous equations
   to find the remaining unknowns.
4. Print the values of the solution vector and stop the program.
## Program:
```
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: HARINI A
RegisterNumber: 212223040056
import numpy as np
import sys
n = int(input())
a = np.zeros((n, n+1))
x = np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
for i in range(n):
    if a[i][i] == 0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio * a[i][k]
x[n-1] = a[n-1][n] / a[n-1][n-1]
for i in range(n-2, -1, -1):
    x[i] = a[i][n]
    for j in range(i+1, n):
        x[i] = x[i] - a[i][j] * x[j]
    x[i] = x[i] / a[i][i]
for i in range(n):
    print('X%d = %0.2f' % (i, x[i]), end=' ')
```

## Output:

<img width="915" height="564" alt="image" src="https://github.com/user-attachments/assets/2e7bd899-dbb1-421b-8b3e-593ba578db4b" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

