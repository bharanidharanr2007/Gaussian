# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1: Form the Augmented Matrix
Combine the coefficient matrix and the constant vector into one augmented matrix.

### Step 2: Forward Elimination
Start with the first row as the pivot row.
Eliminate the entries below the pivot (make them ( 0 )) by subtracting suitable multiples of the pivot row from the rows below.
Move to the next row and repeat the process until the matrix is in row echelon form.

### Step 3: Back Substitution
Starting from the last row, use the pivot positions to solve for one variable at a time.
Substitute the solved values into previous rows to find the remaining variables.



## Program:
```
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n) :
    for j in range(n+1) :
        a[i][j] = float(input())
for i in range(n) :
    if a[i][i]==0.0:
        sys.exit('Divide by zero detected!')
    for j in range(i+1,n) :
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
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![gaussian elimination]()

![image](https://github.com/user-attachments/assets/b9a789fa-5e68-478b-9313-42ebce0134ef)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

