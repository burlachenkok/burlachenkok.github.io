---
layout: post
title: Federated Optimization Algorithms with Random Reshuffling and Gradient Compression
published: true
---

The new paper [Federated Optimization Algorithms with Random Reshuffling and Gradient Compression](https://arxiv.org/abs/2206.07021) has been out.

---

I was glad to work on it with my peers [Abdurakhmon Sadiev](https://www.researchgate.net/profile/Abdurakhmon-Sadiev), [Grigory Malinovsky](https://grigory-malinovsky.github.io/), [Eduard Gorbunov](https://eduardgorbunov.github.io/), [Igor Sokolov](https://cemse.kaust.edu.sa/people/person/igor-sokolov), [Ahmed Khaled](https://rka97.github.io/) and prof. [Peter Richtarik](https://richtarik.org/) from [King Abdullah University of Science and Technology](https://cemse.kaust.edu.sa/) on the paper 
**"Federated Optimization Algorithms with Random Reshuffling and Gradient Compression"**.

The arXiv link for the paper: [https://arxiv.org/abs/2206.02275](https://arxiv.org/abs/2206.07021).

# Abstract

Gradient compression is a popular technique for improving communication complexity of stochastic first-order methods in distributed training of machine learning models. 
However, the existing works consider only with-replacement sampling of stochastic gradients. In contrast, it is well-known in practice and recently confirmed
in theory that stochastic methods based on without-replacement sampling, e.g., Random Reshuffling (<span style="color:rgb(213,40,16)">RR</span>) method, perform better than ones that sample the gradients with-replacement. In this work, we close this gap in the literature and provide the first analysis of methods with gradient compression and without-replacement sampling. 

We first develop a distributed variant of random reshuffling with gradient compression (<span style="color:rgb(213,40,16)">Q-RR</span>), and show how to reduce the variance coming from gradient quantization through the use of control iterates. 

Next, to have a better fit to Federated Learning applications, we incorporate local computation and propose a variant of <span style="color:rgb(213,40,16)">Q-RR</span> called <span style="color:rgb(213,40,16)">Q-NASTYA</span>. <span style="color:rgb(213,40,16)">Q-NASTYA</span> uses local gradient steps and different local and global stepsizes.

Next, we show how to reduce compression variance in this setting as well. Finally, we prove the convergence results for the proposed methods and outline several settings in which they improve upon existing algorithms.

---

<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.png"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/mipt-logo.png"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="75px" src="https://burlachenkok.github.io/materials/princeton-university-logo.png"/> </td>
</tr>
</table>
