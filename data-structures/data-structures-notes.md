### Data Structures:

1. **Arrays and Lists:**
   - Arrays store collections of elements with fixed sizes.
   - Lists in Python are dynamic arrays that can grow or shrink.
   - Access elements by their index, and perform operations like append, insert, remove, and slice.

   ```python
   my_list = [1, 2, 3, 4, 5]
   my_list.append(6)
   my_list.insert(2, 7)
   my_list.remove(3)
   ```

2. **Linked Lists:**
   - A linked list is a sequence of nodes, each containing data and a reference to the next node.
   - Singly linked lists have one reference in each node, while doubly linked lists have two (next and previous).
   
   ```python
   class Node:
       def __init__(self, data):
           self.data = data
           self.next = None

   node1 = Node(1)
   node2 = Node(2)
   node3 = Node(3)
   
   node1.next = node2
   node2.next = node3
   ```

3. **Stacks and Queues:**
   - Stacks follow the Last-In-First-Out (LIFO) principle, like a stack of plates.
   - Queues follow the First-In-First-Out (FIFO) principle, similar to people waiting in a queue.
   
   ```python
   from collections import deque

   # Using a list as a stack
   my_stack = []
   my_stack.append(1)
   my_stack.append(2)
   popped_item = my_stack.pop()

   # Using collections.deque as a queue
   my_queue = deque()
   my_queue.append(1)
   my_queue.append(2)
   dequeued_item = my_queue.popleft()
   ```

4. **Dictionaries (or Hash Maps):**
   - Dictionaries store key-value pairs for efficient data retrieval.
   - Access values by their keys, and perform operations like adding, updating, and deleting entries.
   
   ```python
   my_dict = {'name': 'Alice', 'age': 30, 'city': 'New York'}
   print(my_dict['name'])
   my_dict['country'] = 'USA'
   del my_dict['age']
   ```

5. **Trees and Graphs:**
   - Trees have a hierarchical structure with a root node, branches, and leaves.
   - Common types include binary trees, binary search trees, and AVL trees.
   
   ```python
   class TreeNode:
       def __init__(self, data):
           self.data = data
           self.left = None
           self.right = None

   root = TreeNode(1)
   root.left = TreeNode(2)
   root.right = TreeNode(3)
   ```
