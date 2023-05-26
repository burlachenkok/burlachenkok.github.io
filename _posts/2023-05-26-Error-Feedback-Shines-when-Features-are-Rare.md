---
layout: post
title: Error Feedback Shines when Features are Rare
published: true
---

The new paper [Error Feedback Shines when Features are Rare](https://arxiv.org/abs/2305.15264) has been released.

---

I was glad to work my peers [Elnur Gasanov](https://elnurgasanov.com/) and prof. [Peter Richtarik](https://richtarik.org/) on the paper **"Error Feedback Shines when Features are Rare"**.

The arXiv link for the paper: [https://arxiv.org/abs/2305.15264](https://arxiv.org/abs/2305.15264). 

# Abstract

We provide the first proof that gradient descent (\algname{GD}) with greedy sparsification ($\topk{K}$)  and error feedback (\algname{EF}) can obtain better communication complexity than vanilla \algname{GD} when solving the distributed  optimization problem $\min_{x\in \R^d} \{f(x)=\frac{1}{n}\sum_{i=1}^n f_i(x)\}$, where $n$ = \# of clients, $d$ = \# of features, and $f_1,\dots,f_n$ are smooth nonconvex functions.  
Despite intensive research since 2014  when \algname{EF} was first proposed by Seide et al., this problem remained open until now. %Surprisingly, this superior performance holds in and is facilitated by a heterogeneous data regime. 
Perhaps surprisingly, we show that \algname{EF} shines in the regime when features are rare, i.e., when each feature is present in the data owned by a small number of clients only. To illustrate our main result, we show that  in order to find a random vector $\hat{x}$ such that $\norm{\nabla f(\hat{x})}^2 \leq \varepsilon$ in expectation, \algname{GD} with the $\topk{1}$ sparsifier and \algname{EF} requires  
$\cO\left( \left(L +   \xr\sqrt{ \frac{\xc}{n} \min \left\{ \frac{\xc}{n}  \max_i L_i^2, \frac{1}{n}\sum_{i=1}^n L_i^2 \right\}}  \right) \frac{1}{\varepsilon} \right) $ bits to be communicated by each worker to the server only, where $L$ is the smoothness constant of $f$, 
$L_i$ is the smoothness constant of $f_i$, $\xc$ is the maximal number of clients owning any feature ($1\leq \xc\leq n$), and $\xr$ is the maximal number of features owned by any client ($1\leq \xr \leq d$). Clearly, the communication complexity improves as $\xc$  decreases (i.e., as features become more rare), and can be much better than the $\cO(\xr L \frac{1}{\varepsilon})$ communication complexity of \algname{GD} in the same regime.

---

<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.png"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.png"/> </td> 
</tr>
</table>
