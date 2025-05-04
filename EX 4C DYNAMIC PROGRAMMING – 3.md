# EX 4C DYNAMIC PROGRAMMING – 3
## DATE:17/03/25
## AIM:
Given a sequence, find the length of the longest palindromic subsequence in it.





## Algorithm:

1. Reverse the input string: rev = reverse(seq)
2. Initialize a DP table dp[n+1][n+1] with -1
3. Define a recursive LCS function with memoization:
   * If either length is 0 → return 0
   * If characters match → return 1 + lcs(i-1, j-1)
   * Else → return max(lcs(i-1, j), lcs(i, j-1))
4. Return lcs(n, n) on original and reversed strings


## Program:
```
/*
Program to implement to find the length of the longest palindromic subsequence in it

.
Developed by: SANTHIYA R
Register Number: 212223230192
*/
```
```
dp = [[-1 for i in range(1001)]for j in range(1001)]

def lps(s1, s2, n1, n2):
    if (n1 == 0 or n2 == 0):
        return 0
    if (dp[n1][n2] != -1):
        return dp[n1][n2]
    if (s1[n1 - 1] == s2[n2 - 1]):
        dp[n1][n2] = 1 + lps(s1, s2, n1 - 1, n2 - 1)
        return dp[n1][n2]
    else:
        dp[n1][n2] = max(lps(s1, s2, n1 - 1, n2), lps(s1, s2, n1, n2 - 1))
        return dp[n1][n2]
 
seq = input()
n = len(seq)
s2 = seq
s2 = s2[::-1]
print(f"The length of the LPS is {lps(s2, seq, n, n)}")

```

## Output:

![image](https://github.com/user-attachments/assets/585de86d-ede2-4495-a74b-fd0667b8dec3)


## Result:
Thus the program was executed successfully for finding the length of longest palindromic string.
