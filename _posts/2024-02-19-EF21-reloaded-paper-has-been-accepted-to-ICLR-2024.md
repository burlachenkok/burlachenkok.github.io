---
layout: post
title: "Error Feedback Reloaded: From Quadratic to Arithmetic Mean of Smoothness Constants" has been accepted to ICLR 2024.
published: true
---

["Error Feedback Reloaded: From Quadratic to Arithmetic Mean of Smoothness Constants"](https://arxiv.org/abs/2402.10774) has been accepted to ICLR 2024.

---

Our paper ["Error Feedback Reloaded: From Quadratic to Arithmetic Mean of Smoothness Constants"](https://arxiv.org/abs/2402.10774) has been accepted to The 2024 International Conference on Learning Representations ([ICLR 2024](https://arxiv.org/abs/2402.10774)) proceeding.

The arXiv link for the paper: [https://arxiv.org/abs/2402.10774](https://arxiv.org/abs/2402.10774).

It was more than a great pleasure to work with my peers: [Elnur Gasanov](https://elnurgasanov.com/), [Peter Richtárik](https://richtarik.org/).

## Abstract

Error Feedback (<span style="color:rgb(99,153,89)">EF</span>) is a highly popular and immensely effective mechanism for fixing convergence issues which arise in distributed training 
methods (such as distributed <span style="color:rgb(99,153,89)">GD</span> or <span style="color:rgb(99,153,89)">SGD</span>) when these are enhanced with greedy communication compression techniques such as TopK. 
While <span style="color:rgb(99,153,89)">EF</span> was proposed almost a decade ago ([Seide et al., 2014](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/IS140694.pdf)), and despite concentrated effort by the community to advance the theoretical 
understanding of this mechanism, there is still a lot to explore. 

In this work we study a modern form of error feedback called <span style="color:rgb(99,153,89)">EF21</span> ([Richtarik et al., 2021](https://proceedings.neurips.cc/paper/2021/file/231141b34c82aa95e48810a9d1b33a79-Paper.pdf)) which offers the currently best-known theoretical guarantees, 
under the weakest assumptions, and also works well in practice. In particular, while the theoretical communication complexity of <span style="color:rgb(99,153,89)">EF21</span> depends on the 
quadratic mean of certain smoothness parameters, we improve this dependence to their arithmetic mean, which is always smaller, and can be substantially 
smaller, especially in heterogeneous data regimes. 

We take the reader on a journey of our discovery process. Starting with the idea of applying <span style="color:rgb(99,153,89)">EF21</span> to an equivalent reformulation of the underlying problem
which (unfortunately) requires (often impractical) machine cloning, we continue to the discovery of a new weighted version of <span style="color:rgb(99,153,89)">EF21</span> 
which can (fortunately) be executed without any cloning, and finally circle back to an improved analysis of the original <span style="color:rgb(99,153,89)">EF21</span> method. 
While this development applies to the simplest form of <span style="color:rgb(99,153,89)">EF21</span>, our approach naturally extends to more elaborate variants involving stochastic gradients and 
partial participation. Further, our technique improves the best-known theory of <span style="color:rgb(99,153,89)">EF21</span> in the rare features regime ([Richtarik et al., 2023](https://arxiv.org/abs/2305.15264)).

Finally, we validate our theoretical findings with suitable experiments.

---

## About Event

* [ICLR 2024](https://iclr.cc/)
* **Dates:** May 7th, 2024 to May 11th, 2024
* **Location:** [Messe Wien Exhibition and Congress Center](https://www.messecongress.at/lage/?lang=en), Vienna Austria.

---

<table style="text-align:center;">
<tr>
<table>
<tr>
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td>
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.svg"/> </td>
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/ICLR_Logo.svg"/> </td>
</tr>
</table>
