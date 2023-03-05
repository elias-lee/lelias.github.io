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


🇺🇸 Robert Solow's seminal paper “A Contribution to the Theory of Economic Growth.” was published in 1956. 

There are important assumption that must be set to understand this model 
1. Countries produce and consume a single homogenous good. 
2. technology is exogenous
3. no international trade

# The Basic Solow Model
Solow's model is built around two equations, <mark style="background: #BBFABBA6;">a production function</mark> and <mark style="background: #FF5582A6;">capital accumulation equation.</mark> 

## Production Function
The Production function describes how ***inputs*** combine to produce output.[^1] Inputs are grouped into two categories 💵 capital <mark style="background: #ABF7F7A6;">$K$</mark> and 👷 labor <mark style="background: #ABF7F7A6;">$L$</mark>. The production function is assumed to have a cobb-douglass form. 

$$ Y = F(K,L) = K^\alpha L^{1-\alpha}$$

- $\alpha = [0,1]$  
this means that the function have constant return to scale. [^2]

Now that we have the function we need to define the cost of labor and capital. Lets say firms pay <mark style="background: #ABF7F7A6;">$w$</mark> wage and <mark style="background: #ABF7F7A6;">$r$</mark> rent for each unit of labor and capital respectively. Here we assume perfect competition prevails (firms are price takers). 

$$\max_{K,L} F(K,L)-rK-wL$$

Solving the __*first-order condition*__ firms will hire until <mark style="background: #FF5582A6;">marginal product of labor equals wage and marginal product of capital equals rent</mark>

| Description  | Formula |
|:---------------------------------:|---|
| Hire point (Labor)| $w=\frac{\partial F}{\partial L} = (1-\alpha)\frac{Y}{L}$ |
| Share of output paid to labor   | $w\frac{L}{Y} = 1-\alpha$ |
| Hire point (Capital)            |  $r = \frac{\partial F}{\partial K} = \alpha \frac{Y}{K}$ |
| Share of output paid to Capital | $r\frac{K}{Y}=\alpha$  |

You can see that the factor shares are <color_red> constant</color_red> over time, which is consistent with the Fact 5 from Chapter 1. 


Output per worker \& per capita can be also found as follows: replacing $y \equiv\frac{Y}{L}$ and $k\equiv\frac{K}{L}$ the original function 
$$Y = F(K,L) = K^\alpha L^{1-\alpha}$$
gives us: $y=k^\alpha$

![](https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/econ_growth/cobb-douglas-pf.png?raw=true)



[^1]: Remember production function measures only physical quantities, however this does not mean that output consists only of tangible goods. 

[^2]: Although any value from 0 to 1 is possible Cobb and Douglas proposed that in case of U.S manufacturing $\alpha=\frac{1}{4}$ fits generally very well. 


## Capital Accumulation

Another important important feature of the Solow model is the description of how capital accumulates Solow's proposed capital accumulation equation is define as 

$$\dot K = \overbrace {sY}^{\text{gross investment}} - \overbrace{ \delta K}^{\text{depreciation of capital}}$$

The interpretation of this equation is that the change in capital stock $\dot K$ is equal to the amount of gross investment, $sY$ minus the depreciation rate $\delta K$. 

$\dot K$ is the change in the capital stock per "period". To put it more simply the continuous form of $K_{t+1}-K_t$. 

$$\dot K = \frac{dK}{dt}$$

It is important to highlight that this equation assumes the saving rates to be a <color_red> constant fraction</color_red> of their combine wage and rental income[^3]. Regarding the depreciation rate it also implies that a constant fraction is depreciated every period. The traditional method assumes that a total of 5% is depreciated every year. 
$$\delta = .05$$

There are two easy tricks that are applied to study the growth: take logs and derivatives. This trick can be applied in two ways

Example 1:
$$
\begin{aligned}
k \equiv \frac{K}{L} &\Longrightarrow \log{k} =  \log{K}-\log{L} \\  &\Longrightarrow \frac{\dot k}{k} = \frac{\dot K}{K} - \frac{\dot L}{L}
\end{aligned}
$$ 

Example 1:
$$
\begin{aligned}
y = k^\alpha &\Longrightarrow \log {y} = \alpha \log{k } \\
&\Longrightarrow \frac{\dot y}{y} = \alpha \frac{\dot k}{k}\end{aligned}
$$ 


Now consider the following growth rate $\frac{\dot{L}}{L}$[^4]. The book assumes that labor force is given by $n$. Thus, $\frac{\dot L}{L} = n$

$$L(t) = L_0 e^{nt}$$

Now we will combine $\dot K = sY -  \delta K$ with example one to derive: 
$$
\begin{aligned}
\frac{\dot k}{k} &= \frac{sY}{K} - n - \delta \\
& = \frac{sY}{K} -n - \delta \\ 
\dot k  &= sy - (n+\delta)k
\end{aligned}
$$

This formula can be interpreted as "the change in capital per worker each period is determined by three terms: investment per worker ($sY$) depreciation per worker ($\delta k$) and capital per worker ($nk$)"

[^3]: Individual Total income $Y = wL + rK$. <br>In a closed economy saving = investment and the only purpose of investment is to accumulate capital

[^4]: This book assumes in its major part that the labor force participation rate and the population growth rate is constant. 




## Solving The Basic Solow Model 
TODO:


In short: 
<p style="text-align: center;"> Work pays better in high-income regions </p>






















<!-- ![](https://github.com/elias-lee/lelias.github.io/blob/master/_posts/resources/econ_growth/econ_stats_on_growth.png?raw=true) -->




