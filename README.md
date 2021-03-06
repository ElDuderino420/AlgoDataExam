# Algorithms & Data Structures Exam Preparation 


## Recursion

Bad Recursion BRB



Finite. Deterministic and effective problem-solving method

* The recursion has a **base case**.
* Recursive calls must address subproblems that are smaller in some sense, so that recursive calls converge to the base case.
* Recursive calls should not address subproblems that overlap



Fibonacci numbers using recursion.

```java
public int fibo1(int n) {
        if (n == 1 || n == 2) {
            return 1;
        } else {
            return fibo1(n - 1) + fibo1(n - 2);
        }
    }
```

## Analysis

Time, Memory, Scalability, Big-O, Union-Find Case

##### Big-O:

**Big-O notation** is used in Computer Science to describe the performance or complexity of an algorithm. **Big-O** specifically describes the worst-case scenario, and can be used to describe the execution time required or the space used (e.g. in memory or on disk) by an algorithm. 

| Name         | Description        | Order of Growth | Example           |
| ------------ | ------------------ | --------------- | ----------------- |
| Constant     | Statement          | 1               | Add two numbers   |
| Logarithmic  | Divide in half     | LogN            | Binary Search     |
| Linear       | Loop               | N               | Find the maximum  |
| Linearithmic | Divide and conquer | NlogN           | Mergesort         |
| Quadradic    | Double loop        | N^2             | Check all pairs   |
| Cubic        | Triple loop        | N^3             | Check all triples |
| Exponential  | Exhaustive Search  | 2^N             | Check all subsets |

##### Memory:

| type    | bytes |
| ------- | ----- |
| boolean | 1     |
| byte    | 1     |
| char    | 2     |
| int     | 4     |
| float   | 4     |
| long    | 8     |
| double  | 8     |



## Data Structure

#### Bag:

A bag is a collection where removing items is not supported—its purpose is to provide clients with the ability to **collect items and then to iterate through the collected items** (the client can also test if a bag is empty and find its number of items). 

add, isEmpty, size

#### Queue:

A FIFO queue (or just a queue) is a collection that is based on the first-in-first-out (**FIFO**) policy. The policy of doing tasks in the **same order that they arrive** is one that we encounter frequently in everyday life: from people waiting in line at a theater, to cars waiting in line at a toll booth.

enqueue, dequeue, isEmpty, size

#### Stacks:

A pushdown stack (or just a stack) is a collection that is based on the last-in-first-out (**LIFO**) policy. When you keep your mail in a pile on your desk, you are using a stack. You pile pieces of new mail on the top when they arrive and take each piece of mail from the top when you are ready to read it.  

push, pop, isEmpty, size



#### Array/Linked Lists:

**Definition**. A linked list is a recursive data structure that is either empty (null) or a reference to a node having a generic item and a reference to a linked list.  

```java
private class Node {
 Item item;
 Node next;
}
```

| Data Structure | Advantage                                   | Disadvantage                        |
| -------------- | ------------------------------------------- | ----------------------------------- |
| Array          | index provides immediate access to any item | need to know size on initialization |
| Linked List    | Uses space proportional to size             | need reference to access an item    |



#### Elementary Sorts:

##### Selection sort:

**best case**: *½n^2*

**worst case**: *½n^2* 

One of the simplest sorting algorithms works as follows: First, find the smallest item in the array and exchange it with the first entry (itself if the first entry is already the smallest). Then, find the next smallest item and exchange it with the second entry. Continue in this way until the entire array is sorted. This method is called selection sort because it works by **repeatedly selecting the smallest remaining item**. 

##### Insertion sort:

**best case**: *n*

**worst case**: *½n^2* 

The algorithm that people often use to sort bridge hands is to consider the cards one at a time, **inserting each into its proper place among those already considered** (keeping them sorted). 

##### Shell sort:

Shellsort is a simple extension of insertion sort that gains speed by allowing exchanges of entries that are far apart, to produce partially sorted arrays that can be efficiently sorted, eventually by insertion sort. The idea is to rearrange the array to give it the property that taking every *h*th entry (starting anywhere) yields a sorted sequence. Such an array is said to be *h-sorted*. 

> Why not use selection sort for h-sorting in shellsort?
>
> *Solution.* Insertion sort is faster on inputs that are partially-sorted.

## Merge & Quick Sort

### Merge Sort:

**worst case**: *n log n*

**best case**: *½ n log n*

A simple recursive sort method known as *mergesort*: to sort an array, divide it into two halves, sort the two halves (recursively), and then merge the results. 

Mergesort guarantees to sort an array of N items in time proportional to N log N, no matter what the input. Its prime disadvantage is that it uses extra space proportional to N.

##### Abstract in-place merge. 

##### Top-down mergesort. 

Split into 2 halves, and run merge sort on each half recursively. 

##### Bottom-up mergesort. 

Split array into smallest subarrays (length = 2) and sort, then merge, then increase subarray size.



### Quick Sort:

**Worst case**: *n^2* (/2 ???)

Pivot happens to be biggest or smallest, this would mean doing *n-1* comparisons,

and breaking the list up *n* times

> The standard deviation of the running time is about .65 N, so the running time tends to the average as N grows and is unlikely to be far from the average. The probability that quicksort will use a quadratic number of compares when sorting a large array on your computer is much less than the probability that your computer will be struck by lightning!

**Best case**: *O(n log n)* 

*n* because we have to do *n-1* comparisons,

and log n because we divide the list *n* times

**The basic algorithm**. Quicksort is a divide-and-conquer method for sorting. It works by partitioning an array into two parts, then sorting the parts independently.

 Quicksort works by:

- First selecting a *pivot* number in the array,
- Then sorting the other numbers by placing them before or after the pivot number respectively.
- At this point, the pivot number is in the correct location, and the two groups of numbers (one on each side of the pivot number) still need to be sorted.
- New pivot numbers are then chosen within the remaining subsets, and this process is repeated until no swaps are made.

**Improving**: To insure that the pivot isn't the biggest or smallest, pick a pivot of multiple items and choose the median value to be the pivot.

> - *Cutoff to insertion sort.* As with mergesort, it pays to switch to insertion sort for tiny arrays. The optimum value of the cutoff is system-dependent, but any value between 5 and 15 is likely to work well in most situations.
> - *Median-of-three partitioning.* A second easy way to improve the performance of quicksort is to use the median of a small sample of items taken from the array as the partitioning item. Doing so will give a slightly better partition, but at the cost of computing the median. It turns out that most of the available improvement comes from choosing a sample of size 3 (and then partitioning on the middle item).



## Sorting and Searching

### Priority queues

Priority queues are characterized by the *remove the maximum* and *insert* operations.

isEmpty, add, removeMax, peekMax

| data structure  | insert | remove max |
| --------------- | ------ | ---------- |
| ordered array   | N      | 1          |
| unordered array | 1      | N          |
| binary heap     | log N  | log N      |

**For both insert and remove to be fast, we need to use the binary heap data structure.**

A binary tree is *heap-ordered* if the key in each node is larger than (or equal to) the keys in that nodes two children (if any). 

The largest key in a heap-ordered binary tree is found at the root. 

**Heapsort**. We can use any priority queue to develop a sorting method. We insert all the keys to be sorted into a minimum-oriented priority queue, then repeatedly use remove the minimum to remove them all in order. When using a heap for the priority queue, we obtain heapsort.

### Symbol tables

The primary purpose of a *symbol table* is to associate a *value* with a *key*. The client can *insert* key–value pairs into the symbol table with the expectation of later being able to *search* for the value associated with a given key. 

put, get, delete, contains, isEmpty, size

Examples:

| application | purpose                 | key     | value                |
| ----------- | ----------------------- | ------- | -------------------- |
| dictionary  | find definition         | word    | definition           |
| book index  | find relevant pages     | term    | list of page numbers |
| web search  | find relevant web pages | keyword | list of page names   |

**Linked list (sequential search)** best for tiny symbol tables, slow for large

**Ordered array (binary search)** optimal search and space, order-based ops, slow insert

**Binary search tree** easy to implement, order-based ops, no guarantees space for links

**Hash table** fast search/insert for common types of data, need hash for each type no order-based ops, space for links/empty 

## Search Trees

A ***binary search tree*** (BST) is a binary tree where each node has a `Comparable` key (and an associated value) and satisfies the restriction that the key in any node is larger than the keys in all nodes in that node's left subtree and smaller than the keys in all nodes in that node's right subtree. 

**Balanced Search Trees** is a type of binary search tree where costs are guaranteed to be *logarithmic*. Our trees have near-perfect balance, where the height is guaranteed to be no larger than 2 log N.

* **2-3 search trees.** The primary step to get the flexibility that we need to guarantee balance in search trees is to allow the nodes in our trees to hold more than one key.
  * A *2-node*, with one key (and associated value) and two links 
  * A *3-node*, with two keys and three links 

A ***perfectly balanced* 2-3 search tree** (or 2-3 tree for short) is one whose null links are all the same distance from the root. 

Red-Black BST leads to natural implementation of 2-3 search tree. 

* Red lines represent 3-node connections.

| 2-3 Search Tree | Red-Black BST \| 3-node |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![](https://image.prntscr.com/image/QhZPxyozQ0y2mqPE-dgbpA.png)                                                             |                     ![](https://image.prntscr.com/image/BDF136rvTauh-STh8tQf_A.png)                                         |



## Hash Tables

Hash tables are basically key-value store (or symbol table) with hashed keys.

#### Collision Problems 

Search algorithms that use hashing consist of two separate parts. The first step is to compute a *hash function* that transforms the search key into an array index. Ideally, different keys would map to different indices. 

This ideal is generally beyond our reach, so we have to face the possibility that **two or more different keys may hash to the same array index**. Thus, the second part of a hashing search is a *collision-resolution* process that deals with this situation. 

#### Separate Chaining

If you make an insert into a bucket where a value already resides a list is created (often Linked list)	and the new object is added.

Worst-case scenario is when all the elements of the table’s elements, end up in the same bucket as elements in the list (at which point, you could have used a list instead of a hash table).

**Different strategies for sizing a hash table.**

* We can have a large table, with lots of indices, for very fast search - but at the cost of extra memory.

* Or we can have a small table, with slower searches - but save memory. 

* Or you can resize the lists (the ones inside the hash table’s cells) on the fly, to ensure they have as short a length as possible. 



#### Linear Probing

The simplest open-addressing method is called *linear probing*: when there is a collision (when we hash to a table index that is already occupied with a key different from the search key), then we **just check the next entry in the table** (by incrementing the index). 



As with separate chaining, the performance of open-addressing methods is dependent on the ratio **α = N/M**, but we interpret it differently. 

* For separate chaining α is the **average number of items per list** and is generally larger than 1. 
* For open addressing, α is the **percentage of table positions that are occupied**; it *must* be less than 1. 
* We refer to α as the ***load factor*** of the hash table.

 

#### Clustering

When entries in a hash table clump together (especially with the nature of linear probing)

Resize the table before load factor gets too high. 



#### Symbol table applications

**Dictionary clients** like phone book, dictionary, DNS

**Indexing clients** like web search (keyword, websites), book index (term, page numbers)

![](https://image.prntscr.com/image/aMWeObZbTp6C2tYgIodHFQ.png)

## Swarms

Particle Swarm Optimization (PSO)  algorithm is a population-based search algorithm based on the simulation of the social behavior of birds within a flock.

In PSO particles are "flown" through search space. The changes to a particles within the swarm are influenced by the knowledge of its neighbors. 

**Applications:** PSO has been used mostly to find minima and maxima of nonlinear functions

## Undirected Graphs

A *graph* is a set of *vertices* and a collection of *edges* that each connect a pair of vertices. 

#### Depth first search

**Searching in a maze**

Depth first search explores as far as possible along each branch before backtracking.

Depth-first search is a classic recursive method for systematically examining each of the vertices and edges in a graph. To visit a vertex

* Mark it as having been visited.
* Visit (recursively) all the vertices that are adjacent to it and that have not yet been marked.


| Trace                                                        | Paths                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![depth first search](https://image.prntscr.com/image/LMQhJFT7QMi3YaWccF0-vA.png) | ![depth first search](https://image.prntscr.com/image/YJR-HrzVQ9KRiSLw4DI3QA.png) |


#### Breadth first search

*Depth-first search* finds some path from a source vertex `s` to a target vertex `v`. 

We are often interested in finding **the *shortest* such path** (one with a minimal number of edges). Breadth-first search is a classic method based on this goal. To find a shortest path from `s` to `v`, we start at `s` and check for `v` among all the vertices that we can reach by following one edge, then we check for `v` among all the vertices that we can reach from `s` by following two edges, and so forth. 

| Trace                                                        | Paths                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| ![breadth first search](https://image.prntscr.com/image/tx-VokgJR864BngkX9i5JQ.png) | ![breadth first search](https://image.prntscr.com/image/aEkzpTEsRUWCR-Fp0cQ9UQ.png) |

#### Connected Components

A direct application of depth-first search is to find the connected components of a graph. DFS marks all the vertices connected to a given source.

BFS computes a shortest path from s to v. 



**More applications:**

Cycle detection: is a given graph acyclic? use DFS to determine whether a graph has a cycle.

#### Symbol Graphs

Vertex names are strings. 

## Directed Graphs

A *directed graph* (or *digraph*) is a set of *vertices* and a collection of *directed edges* that each connects an ordered pair of vertices. We say that a directed edge *points from* the first vertex in the pair and *points to* the second vertex in the pair. 



Cycles, connection, reachability

**Reachability in digraphs.** Depth-first search and breadth-first search are fundamentally digraph-processing algorithms.

* *Single-source reachability:* Given a digraph and source `s`, is there a directed path from s to v? (**DFS**)
* *Multiple-source reachability:* Given a digraph and a *set* of source vertices, is there a directed path from *any* vertex in the set to v? (**DFS**)
* *Single-source directed paths:* given a digraph and source `s`, is there a directed path from s to v? If so, find such a path. (**DFS**)
* *Single-source shortest directed paths*: given a digraph and source `s`, is there a directed path from s to v? (**BFS**)

**Cycles and DAGs.** Directed cycles are of particular importance in applications that involve processing digraphs.

* *Directed cycle detection*: does a given digraph have a directed cycle? (**DFS**)

## Minimum Spanning Tree

An *edge-weighted graph* is a graph where we associate *weights* or *costs* with each edge. A *minimum spanning tree (**MST**)* of an edge-weighted graph is a spanning tree whose weight (the sum of the weights of its edges) is no larger than the weight of any other spanning tree. 

* Adding an edge that connects two vertices in a tree creates a unique cycle.

- Removing an edge from a tree breaks it into two separate subtrees.

##### Prim's Algorithm

Prim's algorithm works by attaching a new edge to a single growing tree at each step: Start with any vertex as a single-vertex tree; then add V-1 edges to it, always taking next (coloring black) the minimum-weight edge that connects a vertex on the tree to a vertex not yet on the tree 

**Lazy Implementation**

* Start with one vertex
* Use priority queue for all edges from that vertex sorted by weight
* Add the vertex with the lowest weighted edge to the tree
* Add the edges from the new vertex to the sorted priority queue
* Repeat the adding process
* ![](https://image.prntscr.com/image/zfEYSdlES36kfWJjw-dxGg.png)

The lazy version of Prim's algorithm uses space proportional to **E** and time proportional to **E log E** (in the worst case) to compute the MST 

**Eager Implementation**

- Edges that go to already covered vertices are removed from the priority queue

In short: we maintain on the priority queue just one edge for each non-tree vertex: the shortest edge that connects it to the tree. 

The eager version uses space proportional to **V** and time proportional to **E log V** 

##### Kruskal's Algorithm 

Kruskal's algorithm processes the edges in order of their weight values (smallest to largest), taking for the MST (coloring black) each edge that does not form a cycle with edges previously added, stopping after adding V-1 edges. The black edges form a forest of trees that evolves gradually into a single tree, the MST. 

![](https://image.prntscr.com/image/0waVuuP-Q6uQXcldlaAAXQ.png)

## Shortest Path

https://sinon.org/algorithms/

Nice visual on bottom of page

#### Dijkstra's Algorithm

Finding all shortest paths from a single source with positive weights Iteratively extract closest vertex \(u\) and relax all edges \((u, v)\). The set of vertices is handled using a priority queue.  

(**Like Prim's Algorithm**)

![](https://image.prntscr.com/image/ZWCINs5HTsCqFDcgTkCX9w.png)

#### A* algorithm

Generalizes Dijkstra's with heuristic.