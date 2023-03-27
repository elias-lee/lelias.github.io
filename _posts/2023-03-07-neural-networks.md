---
title: 'NLP study series - Neural Networks'
date: 2023-03-01
permalink: /posts/2023/blog-post-9/
tags:
  - AI
categories:
  - Machine Learning
  - NLP
---

<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@900&display=swap');
  {% include blog_css/nn.css %}
</style>

| Disclaimer: this is a review note contains materials from the following resources.|
| --- | 
|["What is a neural network? Explanation and examples"](https://www.techtarget.com/searchenterpriseai/definition/neural-network) by Ed Burns and John Burke |
| ["Programming for AI (AI504, Fall 2020)"](https://www.youtube.com/watch?v=6Q3AzGDd5oc&list=PLLENHvsRRLjDHllrXj0B8sz5-4xVbisBL&index=5) by prof edward Choi. |
| ["What Is a Neural Network?"](https://www.investopedia.com/terms/n/neuralnetwork.asp) by JAMES CHEN |
| ["What is a neural network?"](https://www.ibm.com/topics/neural-networks) by IBM |
| [An introduction to neural networks](https://developer.ibm.com/articles/l-neural/) by By Andrew Blais, David Mertz|

---

# What is an Artificial Neural Network?

Neural networks (NN) are a subset of Machine Learning (or a means of doing it), in which a computer learns to perform tasks by analyzing training data. NN is the essence of deep learning algorithms.



It's first concept was introduced in 1943 by Warren S. McCulloch & Walter Pitts with the name ["A logical calculus of the ideas immanent in nervous activity"](https://link.springer.com/article/10.1007/BF02478259). However, it did not get much attention until Big Data and increasing computational power allowed to run complex networks. 

## Artificial Neural Network Structure
An ANN is composed of processors operating in layers (tiers) and in parallel. 

<img src = "https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/ml_study/ai504_neural_network.png?raw=true" style="max-width: 100%;">
</p>

An artificial neural network is composed of multiple layers [^1]
1. node-layer [a.k.a input layer] 
2. hidden-layers [singular or plural]
    *  Each layer is highly interconnected with the previous layer. In other words, each node in the layer is connected to many nodes in layer n-1.
3. output layer. 
    * The output layer can have 1 or multiple nodes  

<p align = "left">


[^1]: Each layer has its own weights and threshold.

## How does it work? (an example)
Think of individual as an individual linear regression 
$$Z = w_1x_1 + w_2x_2 + \cdots + w_nx_n + b$$
where $b$ =  bias

Here, the weights determine the importance of each variable. Feeding input variables to the equation above gives you an output that is passed through an activation function such as below.

$$f(x)= 
\begin{cases} 
1 & \text{if } \quad w_1x_1 + w_2x_2 + b >= 0\\ 
0 & \text{if } \quad w_1x_1 + w_2x_2 + b < 0
\end{cases} $$

If the calculated output exceeds a given threshold, it activates or "fires" the node giving an output. The output given becomes the input to the following layer. Each unit doing this job is called <color_red>Threshold logic units (or TLUs)</color_red>.


### How TLU learns

<img src = "https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/ml_study/TLU_with_sigma.gif?raw=true" style="max-width: 100%;">
</p>

As the model go through iteration it adjusts the weight and bias to minimize the loss function eventually reaching a convergence point (or local minimum). The adjustment of weight and bias is possible since each TLU can classify. TLU inputs the results of the inputs into two groups 0 and 1 and iterates until it passes the threshold. 

Weight modification process can be interpreted as below.

```
fully_trained = FALSE
DO UNTIL (fully_trained):
    fully_trained = TRUE
    FOR EACH training_vector = <X1, X2, ..., Xn, theta, target>::
            #Weights compared to theta
        a = (X1  W1)+(X2  W2)+...+(Xn * Wn) - theta
        y = sigma(a)
        IF y != target:
            fully_trained = FALSE
        FOR EACH Wi:
        MODIFY_WEIGHT(Wi)          #According to the training rule 
```
> source: Andrew Blais, David Mertz (2001)

When you use $w_i =  \alpha (t - y) x_i$ is called a perceptron[^2]. 

[^2]: Since they use a perceptron learning rate

## Rules to optimize weights

### Perceptron rule 
The perceptron rule is based on the idea that weight modification is best determined by: some fraction of the difference between target and output. 


### Delta rule
Delta rule is based on gradient descent. In weight modification, a neural net can seek a weight distribution that minimizes error.


If the NN is to execute an supervised-learning you'll want to evaluate the accuracy of the trained data, the function that do this job is called a loss (or cost) function. 

### Back-propagation
Is an extension of the analysis in the delta rule to NN with Hidden nodes.


## Types of Neural Network
### Feed-Forward Neural Networks (a.k.a Multilayer perceptron)
Is considered one of the simplest forms of neural network. It passes information through ***one direction*** until it reaches the output layer. When every neuron has a connection with the node of the previous layer output, it is also known as Fully Connected Network (FNN) or Dense Network.

### Recurrent Neural Networks ⭐️⭐️
Neural networks take the output of a processing node and feeds the information back into the network. Improving the network by a "learning process".

### Convolutional Neural Networks ⭐️⭐️⭐️
Have several layer in which data is sorted into categories. The model has an input layer, an output layer, and a hidden layer composed of single or multiple ***convolutional layers***. 
* The convolutional layers can be entirely connected or pooled

### Deconvolutional Neural Networks
You can think as the reversed version of CNN. The purpose of this model is to find lost features or signals that may have originally been considered unimportant.

### Modular Neural Networks
Is multiple neural networks working separately from one another. 
