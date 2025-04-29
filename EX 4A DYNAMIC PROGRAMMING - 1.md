# EX 4A DYNAMIC PROGRAMMING - 1
## DATE: 14/03/25
## AIM:
To find longest common subsequence using Dynamic Programming.

## Algorithm

1. If either string is empty, return `0`.  
2. If last characters of both strings match Return `1 + LCS of remaining parts`.  
3. Else Return `max(LCS without last char of X, LCS without last char of Y)`.  
4. Repeat recursively until base case is reached.  
5. Final result is the LCS length.

## Program:
```
/*
Program to implement the longest common subsequence using Dynamic Programming
Developed by: SANTHIYA R
Register Number:  212223230192
*/
```
```
def lcs(X, Y, m, n):
	if m == 0 or n == 0:
	    return 0;
	elif X[m-1] == Y[n-1]:
	    return 1 + lcs(X, Y, m-1, n-1);
	else:
	    return max(lcs(X, Y, m, n-1), lcs(X, Y, m-1, n));

X = input()
Y = input()
print ("Length of LCS is ", lcs(X, Y, len(X), len(Y)))
```

## Output:
![image](https://github.com/user-attachments/assets/5d30c33a-037c-4b17-94f7-2c443b8bda6c)



## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
