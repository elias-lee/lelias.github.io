---
title: 'Introduction to Economic Growth Series-The Solow Model'
date: 2020-06-10
permalink: /posts/2020/blog-post-7/
tags:
  - Charles I. Jones
categories:
  - Economic Policy
  - Economic Growth
  - Public Policy
---
<!-- Local 에서 보면서 editing 하려면 includes에서 불러와야함. 단, Github url 문제로 Deploy상에는 정상적으로 import가 안됨으로 
로컬용으로 include코드를 추가하고
Github용으로는 link tag를 추가함-->
<!-- <link href="{{ site.baseurl }}/lelias.github.io/assets/css/econ_series.css" rel="stylesheet"> -->

<style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@900&display=swap');
  {% include blog_css/econ_series.css %}
</style>

This series is a summary of the text book "Introduction to Economic Growth" by CHARLES I. JONES and DIETRICH VOLLRATH.

<p align = "left">
  <img src = "https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/econ_growth/econ_growth_cover.png?raw=true" style="max-width: 30%;">
</p>

Robert Solow's seminal paper “A Contribution to the Theory of Economic Growth.” was published in 1956. 

There are important assumption that you must set to understand this model 
- Countries produce and consume a single homogenous good. 
- technology is exogenous
- no international trade

## The Basic Solow Model
Solow's model is built around two equations, <mark style="background: #BBFABBA6;">a production function</mark> and <mark style="background: #FF5582A6;">capital accumulation equation.</mark> 

### Production Function
The Production function describes how ***inputs*** combine to produce output.[^1] Inputs are grouped into two categories capital <mark style="background: #ABF7F7A6;">$K$</mark>  and labor <mark style="background: #ABF7F7A6;">$L$</mark>. The production function is assumed to have a cobb-douglass form. 

$$ Y = F(K,L) = K^\alpha L^{1-\alpha}$$

- $\alpha = [0,1]$  
this means that the function have constant return to scale. [^2]

Now that we have the function we need to define the cost of labor and capital. Lets say firms pay <mark style="background: #ABF7F7A6;">$w$</mark> wage and <mark style="background: #ABF7F7A6;">$r$</mark> rent for each unit of labor and capital respectively. Here we assume perfect competition prevails (firms are price takers). 

$$\max_{K,L} F(K,L)-rK-wL$$

Solving the __*first-order condition*__ firms will hire until <mark style="background: #FF5582A6;">marginal product of labor equals wage and marginal product of capital equals rent</mark>

$$w=\frac{\delta F}{\delta L} = (1-\alpha)\frac{Y}{L}, \\ \ \\ \text{Share of output paid to labor} \qquad w\frac{L}{Y} = 1-\alpha\\ \ \\ r = \frac{\delta F}{\delta K} = \delta \frac{Y}{K} \\ \ \\ \text{Share of output paid to capital} \qquad r\frac{K}{Y}=\alpha$$ 


Now what we are really interested is in finding output per worker or per capita output thus replacing $y \equiv\frac{Y}{L}$ and $k\equiv\frac{K}{L}$ the original function [$Y = F(K,L) = K^\alpha L^{1-\alpha}$] gives us: 

$$y=k^\alpha $$

![World GDP Growth Rate](https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/econ_growth/cobb-douglas-pf.png?raw=true)



### Capital Accumulation
<!-- TODO: from page 24  -->


















[^1]: Remember production function measures only physical quantities, however this does not mean that output consists only of tangible goods. 

[^2]: Although any value from 0 to 1 is possible Cobb and Douglas proposed that in case of U.S manufacturing $\alpha=\frac{1}{4}$ fits generally very well. 















![](https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/econ_growth/econ_stats_on_growth.png?raw=true)


In short: 
<p style="text-align: center;"> Work pays better in high-income regions </p>


