---
layout: post
title: Predictive Distributions (BDA 3rd Edition, Chapter 2) 
category: Data-Science-1
lang: EN
description: This post explores Exercise 2 in Chapter 2
sticky: false
---

This post provides an answer for Exercise 2 from Chapter 2 of [_**Bayesian Data Analysis (BDA) 3rd Edition**_](http://www.stat.columbia.edu/~gelman/book/BDA3.pdf). Let's state the problem from the _beloved_ book.   

Consider two coins, $C_1$ and $C_2$, with the following characteristics:     

$$\begin{align}
\Pr(\text{head} \mid C_1) &= 0.6, \\
\Pr(\text{head} \mid C_2) &= 0.4.     
\end{align}$$

Choose one of the coins at random and imagine spinning it repeatedly.     
Here is the question: 

> Given that the **first two spins** from the chosen coin are **tails**, what is the **expectation of the number of additional spins until a head shows up**?

To simplify our writing, we denote $\text{head}$ and $\text{tail}$ as $H$ and $T$ respectively. Therefore, we have

$$
  \begin{align*}
    C_1 &\rightarrow \Pr(H \mid C_1) = 0.6 = \frac{3}{5}, \tag{1}\label{eq:c1}\\
    C_2 &\rightarrow \Pr(H \mid C_2) = 0.4 = \frac{2}{5}. \tag{2}\label{eq:c2}
  \end{align*}
$$

[![img1]({{ site.baseurl }}/assets/images/the-experiment.png){:class="img-responsive"}]({{ site.baseurl }}/assets/images/the-experiment.png)*<center>$\pmb{\text{Figure 1}}$: The problem poses an experiment consisting of two steps. Specifically, $N \sim$ geometric distribution.</center>*
    

If we read the problem carefully, we may find that the problem consists of two steps as depicted in $\pmb{\text{Figure 1}}$. Particularly, random variable $N$ is a geometric distribution which has a _probability mass function_ such that

$$
  \begin{equation}
    \Pr(n) = (1-C_i)^{n-1} C_i \tag{3}\label{eq:pmf-geometri}
  \end{equation}
$$
where $C_i$ depends on either $C_1$ or $C_2$.    
    
Now, let us compute
   $$ \begin{equation}
    E(N \mid TT) = ? \tag{4}\label{eq:problem} 
   \end{equation}$$
as shown

$$
  \begin{align}
    \text{E}(N \mid TT) &= \int N \, \Pr(N \mid TT) \, dN && \text{by definition} \tag{5}\label{eq:compute-1} \\ 
                   &= \int \int N \, \Pr(N, C \mid TT) \, dC \, dN && \text{by Bayes rule} \tag{6}\label{eq:compute-2} \\ 
                   &= \int \int N \, \Pr(N \mid TT,C) \Pr(C \mid TT) \, dC \, dN && \text{by conditional probability} \tag{7}\label{eq:compute-3} \\ 
                   &= \int \underbrace{\int N \, \Pr(N \mid TT,C) \, dN}_{\text{E}(N \mid TT, C)} \, \Pr(C \mid TT) \, dC && \text{just rearranging} \tag{8}\label{eq:compute-4} \\
                   &= \int \text{E}(N \mid TT, C) \, \Pr(C \mid TT) \, dC && \text{by expectation definition} \tag{9}\label{eq:compute-5} \\
                   &= \sum_{i=1}^2 \text{E}(N \mid TT, C_i) \, \Pr(C_i \mid TT) && \text{since }C \text{ is discrete .}   \tag{10}\label{eq:compute-6}                   
  \end{align}
$$

Recall that $N \sim$ geometric distribution; accordingly, 

$$
  \begin{align}
    \text{E}(N \mid TT, C_i) &= \text{E}(N \mid C_i) && \text{whether we have }TT\text{ as conditional or not} \tag{11}\label{eq:expectation-1} \\
                          &= \frac{1}{C_i}         \tag{12}\label{eq:expectation-2}.
  \end{align}
$$

We proceed from Equation \eqref{eq:compute-6} as shown

$$ \begin{align}
  \text{E}(N \mid TT) &= \text{E}(N \mid TT, C_1) \, \Pr(C_1 \mid TT) +  \text{E}(N \mid TT, C_2) \, \Pr(C_2 \mid TT) \tag{13}\label{eq:final-1} \\
                   &= \frac{1}{C_1} \Pr(C_1 \mid TT) +  \frac{1}{C_2} \Pr(C_2 \mid TT) \tag{14}\label{eq:final-2}   \\
                   &= \frac{1}{C_1} \underbrace{\frac{\Pr(TT \mid C_1) \, \Pr(C_1)}{\Pr(TT)}}_{\text{Part 1}} +  \frac{1}{C_2}  \underbrace{\frac{\Pr(TT \mid C_2) \, \Pr(C_2)}{\Pr(TT)}}_{\text{Part 2}} \tag{15}\label{eq:final-3}   \\
\end{align}
$$

Next, let's compute $\text{Part 1}$ which looks like

$$\begin{align}
  \frac{\Pr(TT \mid C_1) \, \Pr(C_1)}{\Pr(TT)} &= \frac{Pr(TT \mid C_1) \, \Pr(C_1)}{\Pr(TT \mid C_1) \, \Pr(C_1) + \Pr(TT \mid C_2) \, \Pr(C_2)} && \text{expanding }\Pr(TT) \tag{16}\label{eq:part-1-1} \\
     &= \frac{\left( \frac{2}{5} \right) \left( \frac{2}{5} \right) \left(\frac{1}{2} \right)}{\left( \frac{2}{5} \right) \left( \frac{2}{5} \right) \left( \frac{1}{2} \right) + \left( \frac{3}{5} \right) \left( \frac{3}{5} \right) \left( \frac{1}{2} \right)}. \tag{17}\label{eq:part-1-2} \\
\end{align}$$

Similarly, we also calculate $\text{Part 2}$ in the following: 

$$\begin{align}
  \frac{\Pr(TT \mid C_2) \, \Pr(C_2)}{\Pr(TT)} &= \frac{\Pr(TT \mid C_2) \, \Pr(C_2)}{\Pr(TT \mid C_1) \, \Pr(C_1) + \Pr(TT \mid C_2) \, \Pr(C_2)} && \text{expanding }\Pr(TT) \tag{18}\label{eq:part-2-1} \\
     &= \frac{\left( \frac{3}{5} \right) \left( \frac{3}{5} \right) \left( \frac{1}{2} \right) }{ \left( \frac{2}{5} \right) \left( \frac{2}{5} \right) \left( \frac{1}{2} \right) + \left( \frac{3}{5} \right) \left( \frac{3}{5} \right) \left( \frac{1}{2} \right) }. \tag{19}\label{eq:part-2-2} \\
\end{align}$$

Finally, we are able to compute Equation \eqref{eq:problem} as

$$ \begin{align}
  \text{E}(N \mid TT) &= \frac{1}{C_1} \, \text{Part 1} + \frac{1}{C_2} \, \text{Part 2} \tag{20}\label{eq:final-answer}\\
                 &= \frac{1}{3/5} \, \text{Part 1} + \frac{1}{2/5} \, \text{Part 2} \\
                 &= 2.2436   && \text{utilizing Eq. }\eqref{eq:part-1-2}\text{ and Eq. }\eqref{eq:part-2-2} \\
                 &\approx 3 && \text{rounding the number.}
\end{align}$$

This means that in order to _find a head_ after we have two **tails** regardless the coin we choose, we need $\pmb{3}$ more throws **on average**. 