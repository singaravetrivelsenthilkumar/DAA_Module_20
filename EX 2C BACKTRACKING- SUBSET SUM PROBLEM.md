# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To find the number of subsets in an array whose sum is equal to a given target sum using recursion.


## Algorithm
1. Initialize a count to 0 and start with index 0.

2. If the current index equals the array size, check if the sum is 0 and increment the count if true.

3. Recursively include or exclude the current element and adjust the sum accordingly.

4. Return the total count of valid subsets.

5. Print the final result after processing all elements.

## Program:
```py
/*
Program to implement Subset sum problem.
Developed by: SRIRAJ G
Register Number:  212222040161
*/
def subsetSum(arr, n, i,sum, count):
#Write your code here
    if i == n:
        if sum == 0:
            return count + 1
        return count
    
    # Include the current element in the subset
    count = subsetSum(arr, n, i + 1, sum - arr[i], count)
    
    # Exclude the current element from the subset
    count = subsetSum(arr, n, i + 1, sum, count)
    
    return count

arr=[]
size=int(input())
for j in range(size):
    value=int(input())
    arr.append(value)
sum = int(input())
n = len(arr)
 
print(subsetSum(arr, n, 0, sum, 0))
```

## Output:
![image](https://github.com/user-attachments/assets/10357c83-2b77-4606-b13a-db656d1b5cc7)



## Result:
The program prints the number of subsets whose sum is equal to the given target sum.
