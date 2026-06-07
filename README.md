# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. import the required libreries such as NumPy.
2. Create the coefficient matrix and constant metrix using NumPy arrays
3. Apply gaussian elimination to convert the matrix into row echelon form and solve the equations
4. display the solution of the system of equations.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: POOJA A
RegisterNumber: 212225040300'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
def solve_gaussian(data):
    n=int(data[0])
    A=np.array(data[1:],dtype=float).reshape(n,n+1)
    for i in range(n):
        for j in range(i+1,n):
            factor=A[j,i]/A[i,i]
            A[j]-=factor*A[i]
    x=np.zeros(n)
    for i in range(n-1,-1,-1):
        x[i]=(A[i,-1]-np.dot(A[i,i+1:n],x[i+1:n]))/A[i,i]
    return x
data=[]
for i in range(13):
    data.append(input())
result=solve_gaussian(data)
print("".join([f"X{i} = {val:.2f} "for i,val in enumerate(result)]))
```

## Output:
<img width="810" height="491" alt="image" src="https://github.com/user-attachments/assets/c4e3f18d-2d94-4ec7-97e7-b184150f1a28" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

