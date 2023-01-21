- Data Types
- Distance Measures
	- Jaccard
		- Similarity, how similar two sets are. But only takes into account the number of objects, not the content of objects. $$\frac{| S_1 \cap S_1 |}{| S_1 \cup S_2 |}$$
		- Distance between two sets. $$1 - \frac{| S_1 \cap S_1 |}{| S_1 \cup S_2 |}$$
	- LP/Minkowski Distance. As $p \to \infty$ dimensions where the differences are large will start to dominate as they are weighted more. $$\left( \sum_{i=1}^{n} |x_i - y_i|^p \right)^{1/p}$$
	- Cosine. Calculates the angle between two vectors, when we don't care about magnitude, e.g. document similarity irrespective of their size. It is the **dot product** of the two vectors divided by the product of their magnitudes. $$\frac{A \cdot B}{||A|| \ ||B||}$$
	- Edit. The number of changes we have to make to make two strings match.
		ACTGAC
		ACAGAC
		edit distance of 1

- Similarity
	- Longest Common Subsequence, for recursively finding the longest common subsequence among two strings. The idea is that we compare the smallest strings possible which are always strings of length 1, if they match we increase by 1. If the characters don't match, we will start two more recursions, one per string where we move to the next character. Our base case is that we have reached the end of either string, in which case we return 0 to start the count.  
	  ```
	  lcs(s, t, i, j):
		  if s[i] == len(s) or t[j] == len(t)
			  return 0
		  if s[i] == t[j]
			  return 1 + lcs(s, t, i + 1, j + 1)
		  return max(lcs(s, t, i + 1, j), lcs(s, t, i, j + 1)) 
		```
- Nearest Neighbour Search, finding the point that is closest to another point in a set of points.
- Inverted Index
- Clustering
	- Hierarchical.
		- Divise
			  We start with a single cluster and break it up until we end up with k clusters.
		 - Agglomorative
			  Start with k clusters and merge the two closest ones.
		Depending on the similarity measure used, results are different, e.g. min, max, avg, distances.
	- Kmeans. Which partition of clusters minimises our score best? Usually NP complete unless
		- $k = n$
		- $n = 1$
		- $d = 1$ (dimensions)
		Kmeans algorithm, randomly initialise $k$ centroids, assign the closest points to the centroids, recalculate centroids, and repeat until convergence.
	- Kmeans++
		An improved kmeans because the random initialisation of centroids doesn't always produce good results. The centroid initialisation is done such that they are spread more evenly. 
- PCA
- Centrality Measure
	- 
- Page Rank
- Map Reduce