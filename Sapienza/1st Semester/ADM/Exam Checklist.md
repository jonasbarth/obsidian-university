
## Homeworks

- [ ] HW2
	- [x] RQ3
	- [x] RQ8
	- [ ] BQ A
	- [ ] AQ1
	- [ ] AQ2
- [ ] HW3
	- [ ] Parsing
	- [ ] Create Conjunctive Index
	- [ ] Create TF-IDF Index
	- [ ] Query TF-IDF Index
	- [ ] New Score
	- [ ] AQ
- [ ] HW4
	- [ ] algorithmic question
	- [ ] command line
	- [ ] signature matrix of question 1
	- [ ] features for question 2
	- [ ] map reduce kmeans
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
2. Create shingles, i.e. a list of all possible bins `[feature_1_bin_1, feature_1_bin_2...]`
3. Create a one hot vector of each sample wrt the shingles that 