# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:17/03/25
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..



## Algorithm

1. Initialize a 2D array LCSuff` of size (m+1) x (n+1) with zeros.
2. Set result = 0.
3. For each character pair (X[i-1], Y[j-1])
4. Repeat for all i in 1 to m and j in 1 to n.
5. Return `result`.


## Program:
```
/*
Program to implement the longest common substring problem.
Developed by:  SANTHIYA R
Register Number:  212223230192
*/
```
```
def LCSubStr(X, Y, m, n):
    LCSuff = [[0 for k in range(n+1)] for l in range(m+1)]
    result = 0
 
    for i in range(m + 1):
        for j in range(n + 1):
            if (i == 0 or j == 0):
                LCSuff[i][j] = 0
            elif (X[i-1] == Y[j-1]):
                LCSuff[i][j] = LCSuff[i-1][j-1] + 1
                result = max(result, LCSuff[i][j])
            else:
                LCSuff[i][j] = 0
    return result
 
X = input()
Y = input()
m = len(X)
n = len(Y)
print('Length of Longest Common Substring is',LCSubStr(X, Y, m, n))
```
## Output:

![image](https://github.com/user-attachments/assets/ee1706f2-8221-4483-a529-ce393329b76f)


## Result:
Thus the program was executed successfully for finding the longest common substring .
