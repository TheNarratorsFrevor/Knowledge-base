# Part 2: Algorithms and Data Structures

## 1. Introduction

### Insertion Sort

**Algorithm**  
- iterate from index 1 to end  
- compare with sorted subarray to the left  
- shift elements to the right and insert at correct position  

**Python**
```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
```

**Complexity**  
- Best: $O(n)$  
- Average/Worst: $O(n^2)$  
- Space: $O(1)$  

### Growth of Functions

**Asymptotic Notation**  
- $\Theta(g(n))$: tight bound (exact growth rate)  
- $O(g(n))$: upper bound (worst-case)  
- $\Omega(g(n))$: lower bound (best-case)  

---

## 2. Divide and Conquer

### Mergesort

**Algorithm**  
- divide the array into halves  
- recursively sort both halves  
- merge sorted halves  

**Python**
```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        L = arr[:mid]
        R = arr[mid:]
        merge_sort(L)
        merge_sort(R)
        i = j = k = 0
        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1
        arr[k:] = L[i:] + R[j:]
```

**Complexity**  
- All cases: $O(n \log n)$  
- Space: $O(n)$  

### Recursive Factorial

**Python**
```python
def factorial(n):
    return 1 if n == 0 else n * factorial(n - 1)
```

### Binary Search

**Python**
```python
def binary_search(arr, target):
    low, high = 0, len(arr) - 1
    while low <= high:
        mid = (low + high) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1
    return -1
```

recursive:

```python
def binary_search(arr, target, low=0, high=None):
    if high is None:
        high = len(arr) - 1
    if low > high:
        return -1  # not found
    mid = (low + high) // 2
    if arr[mid] == target:
        return mid
    elif arr[mid] > target:
        return binary_search(arr, target, low, mid - 1)
    else:
        return binary_search(arr, target, mid + 1, high)

```

**Complexity**: $O(\log n)$  

---

## 3. Data Structures

### Stack (using list)

```python
stack = []
stack.append(1)  # push
stack.pop()      # pop
```

### Queue (using list)

```python
queue = []
queue.append(1)    # enqueue
queue.pop(0)       # dequeue
```

### Doubly Linked List (dict of dicts)

```python
dll = {
    1: {'prev': None, 'next': 2},
    2: {'prev': 1, 'next': 3},
    3: {'prev': 2, 'next': None}
}
```

### Trees

**Types**
- generic trees  
- binary trees  

**Traversals**
- pre-order: root, left, right  
- post-order: left, right, root  
- in-order: left, root, right  
- breadth-first: level order using a queue  

### Binary Search Tree (BST)

**Operations**
- search  
- min / max  

**Python**
```python
bst = {
    5: {'left': 3, 'right': 7},
    3: {'left': None, 'right': None},
    7: {'left': None, 'right': None}
}
```

---

### Graphs

#### Edge List (list of tuples)

```python
edges = [(0, 1), (1, 2), (2, 0)]
```

**Inspect**  
- number of vertices: `len(set.union(*map(set, edges)))`  
- number of edges: `len(edges)`  
- degree: count appearances of each node  

**Modify**
- insert node: no-op for edge list  
- remove node:
```python
edges = [e for e in edges if node not in e]
```
- insert edge:
```python
edges.append((u, v))
```
- remove edge:
```python
edges.remove((u, v))
```

---

#### Adjacency List (dict of dicts)

```python
graph = {
    0: {1: 1},
    1: {2: 1},
    2: {0: 1}
}
```

**Inspect**
- vertices: `list(graph.keys())`  
- edges: `[(u, v) for u in graph for v in graph[u]]`  
- degree: `len(graph[node])`  

**Modify**
- insert node:
```python
graph[v] = {}
```
- remove node:
```python
graph.pop(v, None)
for u in graph:
    graph[u].pop(v, None)
```
- insert edge:
```python
graph[u][v] = 1
```
- remove edge:
```python
del graph[u][v]
```

---

### Breadth First Search

```python
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])
    while queue:
        node = queue.popleft()
        if node not in visited:
            visited.add(node)
            queue.extend(graph[node])
    return visited
```

**Complexity**  
- edge list: $O(V + E)$ after conversion  
- adjacency list: $O(V + E)$  
