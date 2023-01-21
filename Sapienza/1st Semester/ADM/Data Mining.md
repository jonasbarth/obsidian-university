-   [[#Data Types]]
-   [[#Distance Measures]]
    -  [[#Jaccard Similarity]]
    - [[#Jaccard Distance]]
    -  [[#LP/Minkowski Distance]]
    -  [[#Cosine]]
    -  [[#Edit]]
-   [[#Similarity]]
	- [[#Longest Common Subsequence]]
-   [[#Nearest Neighbour Search]]
-   [[#Inverted Index]]
-   [[#Clustering]]
    -   [[#Hierarchical]]
	    - [[#Divise]]
	    - [[#Agglomorative]]
    -   [[#Kmeans]]
    - [[#Kmeans++]]
-   [[#PCA]]
-   [[#Centrality Measure]]
	- [[#degree centrality]]
	- [[#closeness centrality]]
	- [[#betweenness centrality]]
-   [[#Page Rank]]
-   [[#Map Reduce]]


## Data Types


## Distance Measures

### Jaccard Similarity
How similar two sets are. But only takes into account the number of objects, not the content of objects. $$\frac{| S_1 \cap S_1 |}{| S_1 \cup S_2 |}$$
### Jaccard Distance 
The distance between two sets. $$1 - \frac{| S_1 \cap S_1 |}{| S_1 \cup S_2 |}$$
### LP/Minkowski Distance
As $p \to \infty$ dimensions where the differences are large will start to dominate as they are weighted more. $$\left( \sum_{i=1}^{n} |x_i - y_i|^p \right)^{1/p}$$
### Cosine
Calculates the angle between two vectors, when we don't care about magnitude, e.g. document similarity irrespective of their size. It is the **dot product** of the two vectors divided by the product of their magnitudes. $$\frac{A \cdot B}{||A|| \ ||B||}$$
### Edit
The number of changes we have to make to make two strings match.
```
ACTGAC
ACAGAC
edit distance of 1
```


## Similarity

### Longest Common Subsequence
For recursively finding the longest common subsequence among two strings. The idea is that we compare the smallest strings possible which are always strings of length 1, if they match we increase by 1. If the characters don't match, we will start two more recursions, one per string where we move to the next character. Our base case is that we have reached the end of either string, in which case we return 0 to start the count.  
```
lcs(s, t, i, j):
	if s[i] == len(s) or t[j] == len(t)
		return 0
	if s[i] == t[j]
		return 1 + lcs(s, t, i + 1, j + 1)
	return max(lcs(s, t, i + 1, j), lcs(s, t, i, j + 1)) 
```
## Nearest Neighbour Search
finding the point that is closest to another point in a set of points.

## Inverted Index

## Clustering

### Hierarchical

#### Divise
We start with a single cluster and break it up until we end up with k clusters.

#### Agglomorative
Start with k clusters and merge the two closest ones. Very intensive.
Depending on the similarity measure used, results are different, e.g. min, max, avg, distances.

### Kmeans 
Which partition of clusters minimises our score best? Usually NP complete unless
- $k = n$
- $n = 1$
- $d = 1$ (dimensions)
Kmeans algorithm, randomly initialise $k$ centroids, assign the closest points to the centroids, recalculate centroids, and repeat until convergence.

### Kmeans++
An improved kmeans because the random initialisation of centroids doesn't always produce good results. The centroid initialisation is done such that they are spread more evenly. 
1. Chose the first centre $c_1$ uniformly at random.
2. For each point $x$, find the nearest centre. $$D_s(x) = \min_{c \in C} || x - c ||$$
3. Pick point $x$ with probability $D_s(x)^2$ as the next centre. Squaring means that further away points have a higher probability of being chosen. 

## PCA

## Centrality Measure

### degree centrality
count the number of neighbours each node has and normalise over max neighbours. $$\frac{degree(v)}{n -1}$$
### closeness centrality
Finds nodes that can easily spread information throughout a graph. We normalise over sum the number of hops it takes to get to a node when taking the shortest path, for all other nodes. This is the average length of shortest paths basically and tells us how easy it is to reach this node. We take the reciprocal of it because central nodes should have a larger value. $$\frac{1}{\sum_{u \in V} dist(u, v)} \frac{N - 1}{1}$$
### betweenness centrality
We check how many times a node appears in all possible shortest paths through the network. If it appears often, it means that it is central. $g_v(u, w)$ is the number of shortest paths between nodes $u$ and $w$ that **pass** through $v$. $g(u, w)$ is the number of shortest paths between nodes $u$ and $w$.  $$\sum_{u, w \in V \backslash \{v\}} \frac{g_v(u, w)}{g(u, w)}$$

## Page Rank

Algorithm for determining the rank of a webpage, but can be applied to any graph. The rank of a page is determined by the rank of the pages that point to it. The more important the pages that point to a page are, the more important that page becomes. We do this instead of just counting the pages because this means you just need a lot of incoming links.  $$rank(u) = \sum_{v \to u} rank(v)$$
  
## Map Reduce