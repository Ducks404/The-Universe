>Learning from Experience with Tasks measured by Performance if 
>Performance in Tasks increases with Experience

## Pillars
### Models and Algorithms
>NO knowledge engineers (humans)
### Powerful and Cheaper computation
>Needs this
### Massive data warehouse
> Big Data to train with 

## Process
### Partition to subsets
- #### Training set: Learn the parameters of the model
- #### Test set: Prevent overfitting & Estimate of model quality
### Evaluation of model
- #### Test Splits: eg 80/20 | training, testing
- #### Multiple runs using different partitions
![[Pasted image 20250521180600.png]]


## Data Mining
> Explore and analyse large quantities of data to discover patterns that are :
- Valid: Holds on with new data
- Novel: not obvious
- Useful: can be acted upon
- Understandable: Humans should be able to make sense of it
### Vs Machine learning
> "Don't really care what you do with the data, just want my input and output to match"
- Predictions from data



## Types of tasks
### Supervised vs Unsupervised
![[Pasted image 20250521184710.png]]
#### Both infer functions, but supervised has a target, while unsupervised doesn't

### Supervised
#### Classification
- Categorizes data into classes
##### Decision Tree
- Tree of questions
	- Internal nodes: decision rules on features (decision variable)
	- Leaf nodes: predicted class label
![[Pasted image 20250521190327.png]]

#### Neural Network
- Neurons with directed weighted edges
![[Pasted image 20250521191035.png]]

#### Regression
- Has numerical data as output
- Can be classification if we used the line as a boundary
- Example: Best-fit line

### Unsupervised
#### Clustering
- Group similar objects
- Given unlabelled dataset and similarity metric
- find natural partitioning/groups
#### Association Rules
- Discover correlation between any two or more variables
- Given a set of records of items
- find dependency rules to predict occurrence of one, by another
