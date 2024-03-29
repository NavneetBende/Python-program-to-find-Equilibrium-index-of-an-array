Equilibrium index of an array
Here we will learn about Python program to find Equilibrium index of an array. Equilibrium index of an array is an index such that the sum of elements at lower indexes is equal to the sum of elements at higher indexes.

Method Discussed :
Method 1 : Using Nested loop
Method 2 : Using single loop
Method 3 : Using inbuilt sum() function
Method 1 :
In this method we will use nested loop to find left sum then right sum for every indexes in the given array.

Time and Space Complexity :
Time Complexity : O(n2)
Space Complexity : O(1)
Method 1 : Code in Python
def equilibrium(arr):
    leftsum = 0
    rightsum = 0
    n = len(arr)
 
    for i in range(n):
        leftsum = 0
        rightsum = 0
     
        for j in range(i):
            leftsum += arr[j]
         
        for j in range(i + 1, n):
            rightsum += arr[j]
         
        if leftsum == rightsum:
            return i
     
    return -1
     
# Driver code
arr = [-4, 1, 5, 2, -4, 4, 2]
print ('Equilibrium index is ',equilibrium(arr))
Output
Equilibrium index is 3
Method 2 :
In this method we will use single loop this method is more efficient than the above method 1.

Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(1)
Method 2 : Code in Python
def equilibrium(arr):
 
    total_sum = sum(arr)
    leftsum = 0
    for i, num in enumerate(arr):
         
        total_sum -= num
         
        if leftsum == total_sum:
            return i
        leftsum += num
      
    return -1
     
# Driver code
arr = [-4, 1, 5, 2, -4, 4, 2]
print ('Equilibrium index is ',equilibrium(arr))
Output
Equilibrium index is 3
Method 3 :
In this method we will use inbuilt sum() function to find left indexes value sum and right indexes value sum, then compare them.

Time and Space Complexity :
Time Complexity : O(n)
Space Complexity : O(1)
Method 3 : Code in Python
a=[4, -2, 0, 6, -4]
ans=-1
for i in range(1,len(a)):
    if sum(a[:i])==sum(a[i+1:]):
        ans=i
        break    
print("EQUILIBRIUM INDEX OF AN ARRAY: ")
print(ans)
Output
EQUILIBRIUM INDEX OF AN ARRAY: 2
