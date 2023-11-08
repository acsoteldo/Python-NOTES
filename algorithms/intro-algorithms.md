### Algorithms:

1. **Sorting Algorithms:**
   - Sorting arranges elements in a specific order, like ascending or descending.
   - Common sorting algorithms in Python include `sorted()`, `list.sort()`, and more advanced ones like quicksort and merge sort. Explore [more](https://github.com/acsoteldo/Python-NOTES/blob/main/algorithms/sorting-algorithms.md)
   
   ```python
   my_list = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
   sorted_list = sorted(my_list)
   sorted_list = sorted(my_list, key=lambda x: -x)
   ```

2. **Searching Algorithms:**
   - Searching is finding a specific element in a collection.
   - Linear search checks each element one by one, while binary search is efficient for sorted data.
   
   ```python
   def linear_search(arr, target):
       for index, value in enumerate(arr):
           if value == target:
               return index
       return -1

   def binary_search(arr, target):
       left, right = 0, len(arr) - 1
       while left <= right:
           mid = (left + right) // 2
           if arr[mid] == target:
               return mid
           elif arr[mid] < target:
               left = mid + 1
           else:
               right = mid - 1
       return -1
   ```

3. **Recursion and Recursive Algorithms:**
   - Recursion involves solving a problem by breaking it into smaller, similar subproblems.
   - Base cases are essential to stop the recursion.
   
   ```python
   def factorial(n):
       if n == 0:
           return 1
       else:
           return n * factorial(n - 1)

   def fibonacci(n):
       if n <= 0:
           return 0
       elif n == 1:
           return 1
       else:
           return fibonacci(n - 1) + fibonacci(n - 2)
   ```

4. **Time Complexity and Big O Notation:**
   - Time complexity measures the computational effort required by an algorithm.
   - Big O notation describes how an algorithm's performance scales with input size.
   
   ```python
   def linear_search(arr, target):
       for item in arr:
           if item == target:
               return True
       return False
   # O(n) time complexity

   def binary_search(arr, target):
       # Binary search code
   # O(log n) time complexity
   ```
