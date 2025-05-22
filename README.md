# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
### Step 1:  
Import the required libraries `numpy` and `sys`.  

### Step 2:  
Input the size of the matrix `n` and define augmented matrix `a` as a NumPy array of size `(n, n+1)`. Initialize the solution array `x` as a NumPy array of size `n`.  

### Step 3:  
Perform forward elimination to transform the augmented matrix into an upper triangular form:  
- For each pivot row, ensure the pivot element is non-zero.  
- Subtract multiples of the pivot row from the rows below to eliminate the elements below the pivot.

### Step 4:  
Perform backward substitution to compute the solution:  
- Start with the last variable and substitute back into the equations to find the remaining variables.

### Step 5:  
Display the solution values of all variables using formatted output.

### Step 6:  
Verify the results for correctness.
## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: 212223230171
RegisterNumber: RITHIK V
*/

import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range(n):
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
#black substitution 
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")
```


## Output:

![image](https://github.com/user-attachments/assets/36dbd293-a596-46a0-b52c-1bd66419a429)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

