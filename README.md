# Exp 6 - Gaussian Elimination
## Developed by: Deepak K R
## RegisterNumber: 212225040057

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### step 1: Read the number of unknowns from the user and initialize a zero-filled augmented matrix and a solution array.

### step 2: Populate the augmented matrix by reading the coefficients and constants element by element from the user.

### step 3: Begin forward elimination by iterating through the matrix rows, exiting the program with an error if a zero pivot element is detected.

### step 4: Calculate the elimination ratio and perform row operations to zero out the elements below the main diagonal, forming an upper triangular matrix.

### step 5: Begin back substitution by directly calculating the value of the very last unknown variable.

### step 6: Complete back substitution by iterating backwards through the remaining rows, substituting the already known variables to solve for the rest.

### step 7: Print the final calculated values for all unknown variables, formatted to two decimal places.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Deepak K R
RegisterNumber: 212225040057
*/
import sys
import numpy as np

n = int(input())
a = np.zeros((n,n+1))
x = np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j] = float(input())
        
for i in range(n):
    if a[i][j] == 0.0:
        sys.exit("Divide by zero dectected")
    for j in range(i+1,n):
        ratio = a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k] - ratio*a[i][k]
            
x[n-1] = a[n-1][n] / a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] = x[i] - a[i][j]*x[j]
    x[i] = x[i]/a[i][i]
    
for i in range(n):
    print("X%d = %0.2f"%(i,x[i]),end = " ")
```

## Output:
<img width="952" height="502" alt="image" src="https://github.com/user-attachments/assets/40ed3be6-eff5-42ab-88c5-d44c8f9868a6" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

