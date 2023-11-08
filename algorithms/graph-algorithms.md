### Graph Algorithms
1. **Depth-First Search (DFS):**

   DFS is an algorithm for traversing or searching tree or graph data structures. It starts at the root node and explores as far as possible along each branch before backtracking. Here's a simple example with a graph represented as an adjacency list:

   ```python
   def dfs(graph, node, visited):
       if node not in visited:
           print(node)
           visited.add(node)
           for neighbor in graph[node]:
               dfs(graph, neighbor, visited)

   # Example usage:
   graph = {
       'A': ['B', 'C'],
       'B': ['A', 'D', 'E'],
       'C': ['A', 'F'],
       'D': ['B'],
       'E': ['B', 'F'],
       'F': ['C', 'E']
   }
   visited = set()
   dfs(graph, 'A', visited)
   ```

2. **Breadth-First Search (BFS):**

   BFS is another algorithm for traversing or searching tree or graph data structures. It explores all the neighbor nodes at the present depth before moving to the next level. Here's an example using the same graph:

   ```python
   from collections import deque

   def bfs(graph, start):
       visited = set()
       queue = deque([start])
       visited.add(start)

       while queue:
           node = queue.popleft()
           print(node)

           for neighbor in graph[node]:
               if neighbor not in visited:
                   queue.append(neighbor)
                   visited.add(neighbor)

   # Example usage:
   graph = {
       'A': ['B', 'C'],
       'B': ['A', 'D', 'E'],
       'C': ['A', 'F'],
       'D': ['B'],
       'E': ['B', 'F'],
       'F': ['C', 'E']
   }
   bfs(graph, 'A')
   ```

3. **Dijkstra's Algorithm (shortest path):**

   Dijkstra's algorithm finds the shortest path from a source node to all other nodes in a weighted graph. It uses a priority queue to keep track of the distances. Here's an example:

   ```python
   import heapq

   def dijkstra(graph, start):
       distances = {node: float('inf') for node in graph}
       distances[start] = 0
       priority_queue = [(0, start)]

       while priority_queue:
           current_distance, current_node = heapq.heappop(priority_queue)

           if current_distance > distances[current_node]:
               continue

           for neighbor, weight in graph[current_node].items():
               distance = current_distance + weight
               if distance < distances[neighbor]:
                   distances[neighbor] = distance
                   heapq.heappush(priority_queue, (distance, neighbor))

       return distances

   # Example usage:
   graph = {
       'A': {'B': 1, 'C': 4},
       'B': {'A': 1, 'D': 2, 'E': 7},
       'C': {'A': 4, 'F': 5},
       'D': {'B': 2},
       'E': {'B': 7, 'F': 3},
       'F': {'C': 5, 'E': 3}
   }
   start_node = 'A'
   distances = dijkstra(graph, start_node)
   print(distances)
   ```

4. **Bellman-Ford Algorithm (shortest path with negative weights):**

   Bellman-Ford algorithm is used to find the shortest paths from a single source vertex to all other vertices in a weighted graph, even when negative edge weights are present. Here's an example:

   ```python
   def bellman_ford(graph, start):
       distances = {node: float('inf') for node in graph}
       distances[start] = 0

       for _ in range(len(graph) - 1):
           for node in graph:
               for neighbor, weight in graph[node].items():
                   if distances[node] + weight < distances[neighbor]:
                       distances[neighbor] = distances[node] + weight

       return distances

   # Example usage:
   graph = {
       'A': {'B': 1, 'C': 4},
       'B': {'A': 1, 'D': 2, 'E': -7},
       'C': {'A': 4, 'F': 5},
       'D': {'B': 2},
       'E': {'B': -7, 'F': 3},
       'F': {'C': 5, 'E': 3}
   }
   start_node = 'A'
   distances = bellman_ford(graph, start_node)
   print(distances)
   ```

5. **Kruskal's Algorithm (minimum spanning tree):**

   Kruskal's algorithm is used to find the minimum spanning tree of a connected, undirected graph. It starts with an empty graph and adds edges in ascending order of their weights. Here's an example:

   ```python
   def kruskal(graph):
       def find(parent, node):
           if parent[node] == node:
               return node
           return find(parent, parent[node])

       def union(parent, rank, node1, node2):
           root1 = find(parent, node1)
           root2 = find(parent, node2)
           if rank[root1] < rank[root2]:
               parent[root1] = root2
           elif rank[root1] > rank[root2]:
               parent[root2] = root1
           else:
               parent[root2] = root1
               rank[root1] += 1

       edges = []
       for node in graph:
           for neighbor, weight in graph[node].items():
               edges.append((node, neighbor, weight))
       edges.sort(key=lambda x: x[2])

       minimum_spanning_tree = {}
       parent = {node: node for node in graph}
       rank = {node: 0 for node in graph}

       for edge in edges:
           node1, node2, weight = edge
           root1 = find(parent, node1)
           root2 = find(parent, node2)

           if root1 != root2:
               if node1 not in minimum_spanning_tree:
                   minimum_spanning_tree[node1] = {}
               if node2 not in minimum_spanning_tree:
                   minimum_spanning_tree[node2] = {}
               minimum_spanning_tree[node1][node2] = weight
               minimum_spanning_tree[node2][node1] = weight
               union(parent, rank, root1, root2)

       return minimum_spanning_tree

   # Example usage:
   graph = {
       'A': {'B': 1, 'C': 4},
       'B': {'A': 1, 'D': 2, 'E': 7},
       'C': {'A': 4, 'F': 5},
       'D': {'B': 2},
       'E': {'B': 7, 'F': 3},
       'F': {'C': 5, 'E': 3}
   }
   minimum_spanning_tree = kruskal(graph)
   print(minimum_spanning_tree)
   ```

6. **Prim's Algorithm (minimum spanning tree):**

   Prim's algorithm is another approach to finding the minimum spanning tree of a connected, undirected graph. It starts with an arbitrary node and adds the nearest node with the minimum weight. Here's an example:

   ```python
   def prim(graph):
       visited = set()
       minimum_spanning_tree = {}
       start_node = list(graph.keys())[0]

       while len(visited) < len(graph):
           min_edge = None
           for node in visited:
               for neighbor, weight in graph[node].items():
                   if neighbor not in visited:
                       if min_edge is None or weight < min_edge[2]:
                           min_edge = (node, neighbor, weight)

           if min_edge:
               node1, node2, weight = min_edge
               if node1 not in minimum_spanning_tree:
                   minimum_spanning_tree[node1] = {}
               if node2 not in minimum_spanning_tree:
                   minimum_spanning_tree[node2] = {}
               minimum_spanning_tree[node1][node2] = weight
               minimum_spanning_tree[node2][node1] = weight
               visited.add(node2)

       return minimum_spanning_tree

   # Example usage:
   graph = {
       'A': {'B': 1, 'C': 4},
       'B': {'A': 1, 'D': 2, 'E': 7},
       'C': {'A': 4, 'F': 5},
       'D': {'B': 2},
       'E': {'B': 7, 'F': 3},
       'F': {'C': 5, 'E': 3}
   }
   minimum_spanning_tree = prim(graph)
   print(minimum_spanning_tree)
   ```

These examples should help you understand the basics of these graph algorithms. They are important for various tasks in data science, such as network analysis, recommendation systems, and more.
