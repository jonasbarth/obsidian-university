-   [[#Algorithms]]
-   [[#Analysis]]
-   [[#Running Time]]
-   [[#Optimality]]
-   [[#Recursion]]
-   [[#Dynamic Programming]]
-   [[#Complexity Classes]]
-   [[#Binary Search]]
-   [[#Sorting Algorithms]]
    -   [[#Quicksort]]
    -   [[#Insertion sort]]
    -   [[#Merge sort]]
    -   [[#Heap sort]]
-   [[#Data Structures]]
    -   [[#Queue]]
    -   [[#Stack]]
    -   [[#Heap]]
    -   [[#Priority Queue]]
    -   [[#Linked Lists]]
    -   [[#Dictionary/Hashmap]]
-   [[#Hashing]]
-   [[#Graph Algorithms]]
    -   [[#BFS]]
    -   [[#DFS]]
    -   [[#Dijkstra]]
    -   [[#Mincut]]

 
## Algorithms

## Analysis

## Running Time
$O$ -> bounded above
$\Theta$ -> bounded above and below 

## Optimality

## Recursion

## Dynamic Programming

## Complexity Classes

### Polynomial (P)
Problems that can be **solved** and **verified** in polynomial time $O(n^c)$ 

### **N**ondeterministic-Polynomial (NP)
problems that can be **verified** in polynomial time, but not **solved**. E.g. Hamiltonian cycle.

### **NP Complete**
problems that:
- are in **NP**
- every problem in **NP** can be reduced to

for example, clique problem.

### **NP Hard**
Problems where solutions **cannot** be **verified** in **polynomial** time. E.g. TSP.

## Binary Search

## Sorting Algorithms

### Quicksort 
pick a random pivot, put smaller items to the left and larger items to right of pivot, recursively. $O(n^2)$ with poorly chosen pivots.

### Insertion sort
have a sorted part in the list that we keep adding items into, using pairwise swapping and comparison. $O(n^2$

### Merge sort
divide the array into subarrays and sort when merging. $O(n log n)$

### Heap sort
build max heap of data, remove the root and put at the end of the list, create max heap of `arr[:n-1]`

## Data Structures

### Queue
FIFO

### Stack
LIFO

### Heap
A binary tree where the min/max element can be accessed in constant time.

### Priority Queue
A min/max heap where each element is assigned a priority.

### Linked Lists
A list where insertion is fast but access is slow.

### Dictionary/Hashmap

## Hashing
A one way function to map an object to a bit string. 

## Graph Algorithms

### BFS
Explore all neighbours first. $O(V + E)$

### DFS
Explore a single neighbour first. $O(V + E)$

### Dijkstra
for finding the shortest path between one two nodes in a graph. From the start node, create a path for each neighbouring nodes and calculate the cost. Put everything inside a priority queue and keep appending to the shortest path until you have reached the end node. 

### Mincut
remove edges from a graph to create two disconnected graphs such that the sum/number of the removed edges is the minimum. Randomly merge two nodes, removing all edges that connect the nodes. Keep doing this until we have two nodes left. The edges between the two remaining nodes are the min cut. Since we choose the edges to contract uniformly random, we are unlikely to choose an edge that is part of the min cut.