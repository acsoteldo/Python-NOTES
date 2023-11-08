### Sorting Algorithms

1. **Quick Sort:**

   Quick Sort is a popular and efficient sorting algorithm. It follows the "divide and conquer" approach. Here's a basic implementation in Python:

   ```python
   def quick_sort(arr):
       if len(arr) <= 1:
           return arr

       pivot = arr[0]
       left = [x for x in arr[1:] if x <= pivot]
       right = [x for x in arr[1:] if x > pivot]

       return quick_sort(left) + [pivot] + quick_sort(right)

   # Example usage:
   my_list = [3, 6, 8, 10, 1, 2, 1]
   sorted_list = quick_sort(my_list)
   print(sorted_list)
   ```

2. **Merge Sort:**

   Merge Sort is another efficient sorting algorithm that uses the divide and conquer strategy. It's known for its stability. Here's an example in Python:

   ```python
   def merge_sort(arr):
       if len(arr) <= 1:
           return arr

       mid = len(arr) // 2
       left = arr[:mid]
       right = arr[mid:]

       left = merge_sort(left)
       right = merge_sort(right)

       return merge(left, right)

   def merge(left, right):
       result = []
       i = j = 0

       while i < len(left) and j < len(right):
           if left[i] < right[j]:
               result.append(left[i])
               i += 1
           else:
               result.append(right[j])
               j += 1

       result.extend(left[i:])
       result.extend(right[j:])
       return result

   # Example usage:
   my_list = [38, 27, 43, 3, 9, 82, 10]
   sorted_list = merge_sort(my_list)
   print(sorted_list)
   ```

3. **Bubble Sort:**

   Bubble Sort is a simple sorting algorithm that repeatedly steps through the list and compares adjacent elements, swapping them if they are in the wrong order. It's not the most efficient, but it's easy to understand.

   ```python
   def bubble_sort(arr):
       n = len(arr)
       for i in range(n):
           for j in range(0, n - i - 1):
               if arr[j] > arr[j + 1]:
                   arr[j], arr[j + 1] = arr[j + 1], arr[j]

   # Example usage:
   my_list = [64, 34, 25, 12, 22, 11, 90]
   bubble_sort(my_list)
   print(my_list)
   ```

4. **Insertion Sort:**

   Insertion Sort is another simple sorting algorithm. It builds the final sorted array one item at a time.

   ```python
   def insertion_sort(arr):
       for i in range(1, len(arr)):
           key = arr[i]
           j = i - 1
           while j >= 0 and key < arr[j]:
               arr[j + 1] = arr[j]
               j -= 1
           arr[j + 1] = key

   # Example usage:
   my_list = [12, 11, 13, 5, 6]
   insertion_sort(my_list)
   print(my_list)
   ```

5. **Selection Sort:**

   Selection Sort is a simple in-place sorting algorithm. It repeatedly selects the minimum element from the unsorted portion and places it at the beginning.

   ```python
   def selection_sort(arr):
       for i in range(len(arr)):
           min_index = i
           for j in range(i + 1, len(arr)):
               if arr[j] < arr[min_index]:
                   min_index = j
           arr[i], arr[min_index] = arr[min_index], arr[i]

   # Example usage:
   my_list = [64, 25, 12, 22, 11]
   selection_sort(my_list)
   print(my_list)
   ```
