# EX 4D DYNAMIC PROGRAMMING – 4
## DATE: 21/03/25
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm

1. If either string is empty, return the length of the other (base case).
2. If last characters match, no cost is needed (`cost = 0`).
3. If last characters differ, set `cost = 1`.
4. Recursively compute the minimum 
5. Return the minimum of these three as the result.

## Program:
```
/*
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method

.
Developed by: SANTHIYA R 
Register Number:  212223230192
*/
```
```
def LD(s, t):
    if s == "":
        return len(t)
    if t == "":
        return len(s)
    if s[-1] == t[-1]:
        cost = 0
    else:
        cost = 1
    res = min([LD(s[:-1], t)+1,
               LD(s, t[:-1])+1, 
               LD(s[:-1], t[:-1]) + cost])
    return res
    
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))


```
## Output:

![image](https://github.com/user-attachments/assets/314bba37-29e0-4259-94de-b9468664661c)


## Result:
Thus the program was executed successfully for finding edit distance between two strings.
