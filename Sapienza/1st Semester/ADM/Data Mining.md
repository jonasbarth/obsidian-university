- Data Types
- Distance Measures
	- Jaccard
		- Similarity, how similar two sets are. But only takes into account the number of objects, not the content of objects. $$\frac{| S_1 \cap S_1 |}{| S_1 \cup S_2 |}$$
		- Distance between two sets. $$1 - \frac{| S_1 \cap S_1 |}{| S_1 \cup S_2 |}$$
	- LP/Minkowski Distance. As $p \to \infty$ dimensions where the differences are large will start to dominate as they are weighted more. $$\left( \sum_{i=1}^{n} |x_i - y_i|^p) \right)^{1/p}$$
	- Cosine. Calculates the angle between two vectors, when we don't care about magnitude, e.g. document similarity irrespective of their size. It is the **dot product** of the two vectors divided by the product of their magnitudes. $$\frac{A \cdot B}{||A|| \ ||B||}$$
	- Edit. The number of changes we have to make to make two strings match.
		ACTGAC
		ACAGAC
		edit distance of 1

- Similarity
	- Longest Common Subsequence
- Nearest Neighbour Search
- Inverted Index
- Clustering
	- Hierarchical
	- Kmeans
	- Kmeans++
- PCA
- Centrality Measure
	- 
- Page Rank
- Map Reduce