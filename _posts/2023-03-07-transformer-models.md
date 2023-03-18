---
title: 'ML study series - Transformers'
date: 2023-03-07
permalink: /posts/2023/blog-post-10/
tags:
  - AI
categories:
  - Machine Learning
  - Study
---
Disclaimer: This is a review note of the publication [Attention Is All You Need](https://arxiv.org/abs/1706.03762) by Vaswani et al., 2017

---

Transformers were developed to overcome two major limitations of RNN. 
1. Slow training procedure
2. Difficult to process longer sequences

# Attention mechanism
Unlike previous models, transformers gets rid of labels and utilize attention mechanism to concentrate on words that have close relationship with other words. <br>

Think of the following sentences: 

|I moved the chairs from the room to the storage until it was empty| it = room|
|:---: | :---: |
|I moved the chairs from the room to the storage until it was full| it = garage| 

Attention mechanisms allow machine to find the relationship of words as human naturally do.


# Transformer Architecture
In a typical encoder-decoder model, encoder maps the input sequence of symbol representation $(x_1,\cdots,x_n)$ to a sequence of continuous representation $z = (z_1, \cdots,z_n)$ the decoder then generate an output sequence $(y_1, \cdots, y_n)$ using z.

Transformers architecture is also divided into ***Encoder stack*** and ***Decoder stack***. Encoder stacks (left side of the image below) learns the expressions and the Decoder creates a sentence based on the expressions learned during the Encoding Process.


!["Attention Is All You Need" (Vaswani et al., 2017)](https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/ml_study/transformer_architecture.png?raw=true)

## Encoder

<p align = "left">
  <img src = "https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/ml_study/transformer_encoder.png?raw=true" style="max-width: 50%;">
</p>

### Sub-layers
The encoder consist of N (=6) identical layers that are composed of two sub-layers. 

1. First Sub-layer (Multi-Head self-attention mechanism). 
   * \+ employ residual connection
   * \+ followed by layer normalization
  
2. Second Sub-layer (feed-forward network) 
   * \+ employ residual connection
   * \+ followed by layer normalization


Thus the output of each sub-layer is: 
$$\text{Layer Norm}(x + \text{sub-layer}(x))$$
Where ***$\text{sub-layer}(x)$*** is the function implemented by the sub-layer.

> ❗ all sub-layers, embedding layers produce outputs of dimension $d_{model} = 512$


## Decoder
Decoder also consists of N (=6) stacks of identical layer with three sub-layers. 

1. First sub-layer (Masked multi-head attention [to the output embedding])
   * The first sub layer receive the output from the decoder stack adds positional encoding and implement multi-head attention. 
   * \+ employ residual connection
   * \+ followed by layer normalization

2. Second sub-layer (multi-head attention [to the output of encoder stack])
   * \+ employ residual connection
   * \+ followed by layer normalization

3. Third Sub-layer (feed-forward network) 
   * \+ employ residual connection
   * \+ followed by layer normalization

self-attention sub-layer is modify to attend only subsequent positions. To put it simply, the decoder only attends ***preceding*** words (Prediction for a word at position $i$ can only depend on the known outputs for the words that came before it). 


## Attention function 
Attention function is the mapping of a query ($Q$) and a set of key ($K$) -value ($V$) pairs to an output [query, keys, values, and output are all vectors]

The output is computed as a weighted sum
of the values

<p align = "left">
  <img src = "https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/ml_study/attention_function.png?raw=true" style="max-width: 50%;">
</p>

### Scaled Dot-product attention
The two most commonly used attention functions are additive attention and dot-product attention. The attention function applies a similar dot-product attention with a scaling factor ($\frac{1}{\sqrt{d_k}}$) aggregated. 

The scaled dot-product attention function is used to get the weight value. Input consists of queries and keys of dimension $d_k$ and values of dimension $d_v$. 
To obtain the weight the function applies softmax to the dot product of $Q$ with $K$ divided by the root of the dimension. 

The final matrix of output is:
$$\text{Attention}(Q,K,V) = \text{softmax}(\frac{QK^T}{(\sqrt{d_k)}})V$$

### Multi-head attention
The paper mentions that is more convenient to linearly project the queries, keys and values $h$ times. Thus in this stage concatenates and projects the attention functions performed in parallel yielding $d_v$ dimensional output values (The paper employs a total of 8 heads).  

$$\begin{aligned}
\text{MultiHead(Q,K,V)} &= \text{Concat}(head_1, \cdots, head_h)W^O \\
\text{where }head_i &= \text{Attention}(QW_i^Q,KW_i^K,VW_i^V)
\end{aligned}$$

### Three different characteristics of Transformers attention function. 
1. queries come from the previous decoder layer, and memory keys and values come from the output of the encoder. 
   * mimics the typical encoder-decoder attention mechanisms in sequence-to-sequence models

2. Encoder contains self-attention layers. 
   * keys, values and queries for the self-attention layer come from the output of the previous layer in the encoder

3. self-attention layers in the decoder allow each position in the decoder to attend to all positions in the decoder up to and including that position. 

## Feed-Forward Networks. 
Feed-forward network is applied to each layer in the encoder and decoder separately and identically. 
* FFN consists of two linear transformations with ReLU activation. 
  * $FFN(x) = ReLU (xW_1 + b_1)W_2 + b_2$
* linear transformation are same, but use different parameter from layer to layer. 
* Input and Output dimension is $d_{model} = 512$
* Inner-layer dimension is $d_{ff} = 2048$

## Positional Encoding
Transformers disregards the position of the words. Thus to not lose positional information an additional positional encoding must be injected at the bottoms of the encoder and decoder stacks. 

* Positional encoding vectors have the same dimension as the embeddings. 
* Generated positional encoding vectors are added to the input embedding. 

Although there are many options of positional encoding the paper uses sine and cosine functions of different frequencies:

$$PE_{pos,2i} = sin(pos/100000^{2i/d_{model}})$$
$$PE_{pos,2i+1} = cos(pos/100000^{2i/d_{model}})$$


