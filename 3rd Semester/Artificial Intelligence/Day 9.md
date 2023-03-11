# Day 9
Class: [[COMP6065001 - Artificial Intelligence]]
Session: 18 & 19
Topics: 
- Decision Tree
- Support Vector Machines
Date: 2022-12-15
Lecturer: [[D6416 - PUTI ANDAM SURI, S.Kom, M.TI]]

# Machine Learning

1. Supervised Learning: Labeled data
	1. Decision Tree
	2. Linear Regression
	3. SVMs
2. Unsupervised Learning: Unlabeled data
3. Reinforcement Learning: Reward System

# Decision tree

A basic but powerful iterative algorithm or top-down consruction of a hypothesis.

- Root Node
- Internal Node
- Leaf Node
- Parent and Child nodes

## Information Gain

The standard criterion that is chosen for splitting in decision trees is information gain (the better the split, the higher the information gain)

- Information gain relies on the concept of mutual information: The reduction of entropy of one variable by knowing the other
- We want to maximize mutual information when defining splitting criteria
$$
Gain(D, x_j) = H(D) - \sum_{v \in Values(x_j)} \frac{|D_v|}{|D|}\ H(D_v)
$$

- Where $D$ is the training set of parent node
- $D_v$ is a dataset at a child node upon splitting
- $H(D)$ is entropy of the data, $H(D)$ is entropy of the dataset split

### Entropy

Entropy is a measure of expected "surprise". In Information Theory, entropy is the expected number of bits needed to encode a randomly drawn value of $y$

Entropy Equation:
$$
H(p) = - \sum_{i} p_i log_2 p_i
$$

- **High Entropy**
	- Variable has a uniform like distribution
	- Flat histogram
	- Values sampled from it are less predictable
- **Low Entropy**
	- Distribution of variable has many peaks and alleys
	- Histogram has many lows and highs
	- Values sampled from it are more predictable

# Support Vector Machines

Main objective of SVM is finding  optimal separating [Hyperplane](https://en.wikipedia.org/wiki/Hyperplane). Which maximize margin from training data.

## Properties of SVM
1.  SVMs construct a **maximum margin separator**
2. SVMs create a [linear separating hyperplane](https://kindsonthegenius.com/blog/what-is-a-linear-seperator-what-is-a-hyperplane-simple-and-brief-explanation/), but they have the ability to embed the data into a higher dimensional space, using the so-called [Kernel Trick](https://datamites.com/blog/support-vector-machine-algorithm-svm-understanding-kernel-trick/#:~:text=A%20Kernel%20Trick%20is%20a,linearly%20divided%20by%20a%20plane.)
3. SVMs are a [nonparametric method](https://www.investopedia.com/terms/n/nonparametric-method.asp#:~:text=What%20Is%20the%20Nonparametric%20Method,data%20is%20quantitative%20or%20qualitative.)
