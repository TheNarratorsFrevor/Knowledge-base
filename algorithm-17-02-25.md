### 9:00-11:00  

#### definition of an algorithm  

> "a procedure for solving a mathematical problem in a finite number of steps that frequently involves the repetition of an operation."  

basically, a step-by-step procedure for solving something.  

- then he gave an example of binary search using a dictionary.  

also:  
> an algorithm is a finite, definitive, and effective procedure with some input and some output.  

#### etymology (largely irrelevant)  

- the word "algorithm" comes from "al-khwarizmi."  
- same origin for "algebra," from *al-jabr*, the title of his famous book.  

#### applications  

> tfw you're a pure math enthusiast  

- internet: packet routing, file sharing, etc.  
- biology: i don't care.  
- informatics: circuit design, databases, networking, compilers, etc.  

---

### data structures  

#### arrays  

different shapes of data, the most familiar example is an "array"—a list of integers, floats, or whatever. (technically it's a `<T>`.)  

> then he explained basic pointer/index stuff that i couldn't be assed to write. sorry, future me.  

then a student claimed to have expertise in data analysis but had never heard of an array.  
i fucking hate my life, what am i doing here?  

##### advantages  
- simple and efficient for sequential access  
- supports direct (random) access in O(1) time  
- cache-friendly due to contiguous memory allocation  

##### disadvantages  
- inserting/deleting elements in the middle is O(n)  
- resizing is a pain (requires creating a new array and copying elements)  
- fixed size (unless using dynamic arrays like `vector<T>` in c++)  

---

#### queues  

first in, first out, or **fifo** for short.  

> think of a line at mcdonald's  

##### advantages  
- simple and efficient for tasks requiring fifo order (e.g., task scheduling, bfs in graphs)  
- constant-time enqueue and dequeue (O(1) with a linked list or circular buffer)  

##### disadvantages  
- no direct access to elements (have to dequeue everything to reach an item)  
- fixed size if implemented with an array  

---

#### stacks  

last in, first out, or **lifo** for short. a linear data structure.  
like a stack of plates, papers, or whatnot.  

##### advantages  
- simple and fast (O(1) push and pop)  
- useful for recursive function calls, backtracking, undo mechanisms, etc.  

##### disadvantages  
- limited flexibility, only access to the top element  
- no efficient way to search elements inside  

---

#### linked lists  

basically:  
`node[data, *pNextNode]`  

you can change the pointer to the next node without breaking anything. used a lot.  

##### advantages  
- dynamic size, no need to predefine storage  
- inserting/deleting elements is O(1) if you have a pointer to the correct location  

##### disadvantages  
- no direct access (searching is O(n))  
- extra memory overhead due to pointers  
- cache-unfriendly (non-contiguous memory allocation)  


#### trees  

a hierarchical data structure with a root node, where each node has child nodes.  
binary tree: each node has at most two children.  
parent: has children
leaf: at the end, dangling, no children but *yes parent*.
binary search tree (bst): left child i s smaller, right child is greater.  

##### advantages  
- efficient searching (O(log n) in a balanced tree)  
- good for hierarchical data (e.g., file systems, xml parsing)  
- insert/delete operations are relatively fast compared to arrays (O(log n) in a balanced tree)  

##### disadvantages  
- unbalanced trees degrade to linked lists (O(n) operations)  
- requires extra memory for pointers  
- more complex than linear structures  

#### graph

A general form of trees, where there is no root node. connections are in the range of $0$ to $n-1$. 


---
> Anything beyond this line is added, not covered in the lecture
---


#### doubly linked lists  

basically like a linked list but each node has a pointer to both the next **and** the previous node:  
`node[data, *pPrevNode, *pNextNode]`  

##### advantages  
- can traverse in both directions  
- deletion is easier because you can move backward too  

##### disadvantages  
- even more memory overhead (extra pointer per node)  
- still O(n) search time  

#### Book:

Just read O'Reily for python.
CLRS: intro to algorithms and data structures (third edition)

---

#### circular linked lists  

like a linked list, but the last node points back to the first, making it cyclic.  

##### advantages  
- can traverse indefinitely without worrying about the end  
- good for round-robin scheduling  

##### disadvantages  
- easy to screw up and make an infinite loop  
- still O(n) search time  


#### balanced trees  

trees that maintain balance to keep operations efficient.  
examples:  
- **avl tree**: self-balancing binary search tree (rotates to stay balanced)  
- **red-black tree**: another self-balancing tree, used in maps/sets in std libraries  

##### advantages  
- guarantees O(log n) search, insert, and delete times  
- prevents worst-case O(n) degradation of bst  

##### disadvantages  
- rotations make insertions and deletions more complex  
- slightly higher overhead compared to unbalanced trees  

---
#### heaps  

a specialized tree where the parent node is always greater (max heap) or smaller (min heap) than its children.  
used for priority queues.  

##### advantages  
- fast retrieval of min/max element (O(1))  
- insertions/deletions are O(log n)  

##### disadvantages  
- not great for general searching (O(n))  
- requires extra memory for tree structure  

---