
## Homeworks

- [ ] HW2
	- [x] RQ3
	- [x] RQ8
	- [x] BQ A
	- [ ] AQ1
	- [ ] AQ2
- [ ] HW3
	- [x] Parsing
	- [x] Create Conjunctive Index
	- [x] Create TF-IDF Index
	- [x] Query TF-IDF Index
	- [x] New Score
	- [x] AQ
- [ ] HW4
	- [ ] algorithmic question
	- [ ] command line
	- [x] signature matrix of question 1
	- [x] features for question 2
	- [x] map reduce kmeans
- [x] HW5
	- [x] Functionality 1
	- [x] Functionality 4
	- [x] Visualisation 4
	- [x] Visualisation 5
	- [x] Algorithmic Question

## HW3

### LSH
Local Sensitivity Hashing is a method for dimensionality reduction.

How?
1. Bin each feature
2. Create shingles, i.e. a list of all possible bins `[feature_1_bin_1, feature_1_bin_2, feature_2_bin1...]`
3. Create a shingle matrix where rows are one hot vectors of each sample wrt the shingles that they have `[0, 1, 1...]`. 
4. Transpose the shingle matrix such that shingles are rows and samples are columns.
5. For each row in the transposed matrix, find the index of the column where we find the first 1, and create a vector of them. This is the minhash procedure.
6. The vector becomes a row in the signature matrix. Each column in the signature matrix corresponds to a data sample.
7. Permute the rows of the shingle matrix and repeat the process of finding the index of the column of the first 1.
8. Divide the signature matrix into $b$ bands where each band has $r$ rows. 
9. For each column (data sample), we look at each band and place it into a bucket. Two bands that have the same values will end up in the same bucket. A small $b$ means that each bands has a large number of rows $r$, and most documents will be considered to be similar. A large $b$  means that each band has a small number of rows $r$ and most documents will be considered differently.

When running a query to find similar elements, we repeat these steps and then see which bucket the query ends up in. 