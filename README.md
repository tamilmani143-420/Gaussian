# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Input the number of equations and form the augmented matrix with coefficients and constants.

2. Apply forward elimination to convert the matrix into an upper triangular form by eliminating lower elements using row operations.

3. Perform back substitution starting from the last equation to find each variable sequentially.

4. Display the computed values of all unknowns as the final solution.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: THAMIZHMANI M
RegisterNumber: 212225040468
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=" ")
```

## Output:
<img width="1422" height="849" alt="Screenshot 2026-05-20 182639" src="https://github.com/user-attachments/assets/2f10a532-8549-4439-86c2-cafa3d816d71" />
<img width="1428" height="831" alt="Screenshot 2026-05-20 182702" src="https://github.com/user-attachments/assets/28f897d3-429b-4760-9e7f-e7e781816ab4" />
<img width="1419" height="268" alt="Screenshot 2026-05-20 182718" src="https://github.com/user-attachments/assets/76e579bd-38af-43ab-b095-e0d9591be25e" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

