Create algorithms that mimic behavior seen in real life

## Popular Examples
### 1. Genetic Algorithm
survival of the fittest

### 2. Particle Swarm
emulates bird swarms

### 3. Neural Network
Nodes transforming input into desired output
[Neural Networks for babies](https://www.amazon.com/Neural-Networks-Babies-Baby-University/dp/1492671207)


## Neural Network
### Supervised Learning
Needs dataset, teaches Neural Network by guiding it with right or wrong

### Unsupervised Learning
Used to discover more patterns that humans can't see
E.g.: [Restricted Boltzmann Machine](https://scikit-learn.org/stable/modules/neural_networks_unsupervised.html)

### Structure
- #### Input Layer
Same number of nodes as inputs
- #### Output Layer
Same number of nodes as output/corresponding
- #### Hidden Layer
Main action and can vary in regards to depth

### Math
![[Pasted image 20231225075648.png]]
Input is multiplied by a **weight** and added up.
This value is then put through an **activation function** which maps the values to a value between 0 and 1 or -1 and 1 (active/inactive)

### Training Steps
#### Feed-Forward loop
- After training, only this step is done
- Sending data through network and getting an answer out the other side
##### Steps
1. Normalise input data into same range
2. Give all input data to each node of next layer
3. Multiply weight, add, activation func
4. Give to next layer, loop

#### Back-propagation
- After each feed, tell network how right/wrong they are
- Update the weights

##### Steps
1. Calculate difference between output and desired output
2. Adjust weight of previous nodes based on this difference
3. Continue to propagate until the input node weights get changed

### Dataset Splits
#### Problem: Overtraining
Occurs when neural network is only learning the answers and not how to get to the answer

#### Solution: Dataset Splits
- Training Data: 70-80%
	Used to train, feed-forward and back-propagation
- Validation Data: 10-15%
	Tests after each training round to check if declining, aka overtraining
- Testing Data: 10 - 15%
	Only tests at the end

### Making the Neural Network
Reference [[14-The Code.py|the Code]]
1. Import libraries
	- [Pandas](https://pandas.pydata.org/) to use databases
	- [scikit-learn](https://scikit-learn.org/) to make neural network
2. Load the datasets
3. Make sure input is numbers
4. 