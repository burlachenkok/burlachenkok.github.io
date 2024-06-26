---
layout: post
title: Sharper Rates and Flexible Framework for Nonconvex SGD with Client and Data Sampling
published: true
---

The new paper [Sharper Rates and Flexible Framework for Nonconvex SGD with Client and Data Sampling](https://arxiv.org/abs/2206.02275) has been outed.

---

I was glad to work my peers [Alexander Tyurin](https://k3nfalt.github.io/), [Lukang Sun](https://lukangsun.github.io/), and prof. [Peter Richtarik](https://richtarik.org/) from [King Abdullah University of Science and Technology](https://cemse.kaust.edu.sa/) on the paper **"Sharper Rates and Flexible Framework for Nonconvex SGD with Client and Data Sampling"**.
The arXiv link for the paper: [https://arxiv.org/abs/2206.02275](https://arxiv.org/abs/2206.02275).

During numerical experiments for that paper, we heavily exploited **FL_PyTorch** -- an advanced research simulator for Federated Learning:

* [https://dl.acm.org/doi/10.1145/3488659.3493775](https://dl.acm.org/doi/10.1145/3488659.3493775)
* [FL_PyTorch presentation at rising starts in AI Symposium](https://burlachenkok.github.io/FL_PyTorch-presentation-at-rising-starts-in-AI-Symposium/) 

# Abstract

We revisit the classical problem of finding an approximately stationary point of the average of $$n$$ smooth and possibly nonconvex functions.
 
The optimal complexity of stochastic first-order methods in terms of the number of gradient evaluations of individual functions is $$\mathcal{O}(n + \sqrt{n}/\varepsilon)$$, attained by the optimal SGD methods <span style="color:rgb(74,126,104)">SPIDER</span> [[Fang et al, NeurIPS 2018](https://arxiv.org/abs/1807.01695)] and <span style="color:rgb(74,126,104)">PAGE</span> [[Zhize et al, ICML 2021](https://arxiv.org/abs/2008.10898)], for example, where $$\varepsilon$$ is the error tolerance. 

However, i) the big-$$\mathcal{O}$$ notation hides crucial dependencies on the smoothness constants associated with the functions, and ii) the rates and theory in these methods assume simplistic sampling mechanisms that do not offer any flexibility. In this work we remedy the situation. 

First, we generalize the <span style="color:rgb(74,126,104)">PAGE</span> algorithm so that it can provably work with virtually any (unbiased) sampling mechanism. 
This is particularly useful in federated learning, as it allows us to construct and better understand the impact of various combinations of client and data sampling strategies. 

Second, our analysis is sharper as we make explicit use of certain novel inequalities that capture the intricate interplay between the smoothness constants and the sampling procedure. 

Indeed, our analysis is better even for the simple sampling procedure analyzed in the <span style="color:rgb(74,126,104)">PAGE</span> paper. However, this already improved bound can be further sharpened by a different sampling scheme which we propose. 

In summary, we provide the most general and most accurate analysis of optimal SGD in the smooth nonconvex regime. Finally, our theoretical findings are supposed with carefully designed experiments.

---

<center>
<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
</tr>
</table>
</center>