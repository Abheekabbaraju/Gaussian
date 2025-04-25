# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the NumPy module to work with matrices.
2. Define the augmented matrix using np.array() which includes both coefficients and constants
3. Apply row operations manually or programmatically to convert the matrix into row echelon form (upper triangular).
4. Perform back-substitution to find the values of the variables.
5. Display the solution and end the program.

## Program:
```python
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: abheek.a
RegisterNumber: 212224100001
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
for i in range(n):
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n):
        ratio =a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')

```

## Output:
![Screenshot 2025-04-25 152928](https://github.com/user-attachments/assets/612e4d81-9d60-4882-8284-797e1bed854d)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

