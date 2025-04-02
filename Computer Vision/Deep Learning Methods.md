### Pipeline
Input -> Learned features <-> Machine Learning <-> Output


### Supervised Learning
- Training is processed in the labeled dataset
- Learns from labeled input data
- After being given new data, it uses features from learned dataset for classification

### Bayesian Classification
- Calculates probability that a given `X` belongs to the class `Ck`
- `lk = log*p(x|Ck) + log*p(Ck)`

### Logistic Regression
- Maximizes likelihood of correct labels by minimizing negative log likelihood
- Utilizes entropy loss functions that penalize incorrect predictions

### Support Vector Machines
- Tries to find a plane in 3-D space that most accurately separates classifications in a correct way.
- Also maximizes the margin (distance from plane to closest element), while minimizing the loss function
- Very used for binary classification
- Since misclassified data is very common, we use a sigma value, where sigma > 1 = correct classification. 1 > sigma > 0 = not sure, and less than 0 means incorrect classification.
### Unsupervised Learning
- Based on similarity on input data.
1) Initialize centroid randomly
2) Compute distance between data point to each and every data point
3) Assign data point to closest centroid
4) Calculate mean of all distances to a centroid and shift centroid according to that mean
5) Repeat until convergence.

### Semi-supervised learning
- works with both labeled and unlabeled data.
1) Apply un-supervised learning
2) Perform pseudo-labeling with learned information
3) Train based on labeled and pseudo-labeled data.

### Deep Neural Networks
- Output of each neuron can serve as the input to the next one.