---
layout: post
title: Don't Compress Gradients at NeurIPS 24

published: true

---

Paper "Don't Compress Gradients in Random Reshuffling: Compress Gradient Differences" has been accepted at NeurIPS 2024.

---

<center>
<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="80px" src="https://burlachenkok.github.io/materials/neurips-logo.svg"/> </td>
</tr>
</table>
</center>

Our recent research work **"Don't Compress Gradients in Random Reshuffling: Compress Gradient Differences"** has been accepted for presentation and proceedings at [Conference on Neural Information Processing Systems (NeurIPS) 2024](https://neurips.cc/Conferences/2024/). This year, the NeurIPS main track received a total of 15,671 valid paper submissions, from which the program committee accepted only 25.8%.

An earlier version of this work was published on arXiv under the title **"Federated Optimization Algorithms with Random Reshuffling and Gradient Compression."**. We have since updated the title to better reflect our research.

I am grateful to have collaborated with my talented peers: [Abdurakhmon Sadiev](https://www.researchgate.net/profile/Abdurakhmon-Sadiev), [Grigory Malinovsky](https://grigory-malinovsky.github.io/), [Eduard Gorbunov](https://eduardgorbunov.github.io/), [Igor Sokolov](https://cemse.kaust.edu.sa/people/person/igor-sokolov), [Ahmed Khaled](https://rka97.github.io/), and Professor [Peter Richtarik](https://richtarik.org/). 

# Links

[1] You can find our submission here:  [https://openreview.net/forum?id=CzPtBzgfae](https://openreview.net/forum?id=CzPtBzgfae)

[2] An earlier version of the paper is available here: [https://arxiv.org/abs/2206.07021](https://arxiv.org/abs/2206.07021)

[3] The work will be presented  at NeurIPS 2024 which will be held at the [Vancouver Convention Center, Vancouver, Canada](https://maps.app.goo.gl/XCrE3Q9ibkWK8LER9) in the form of a poster


---

# Abstract

Gradient compression is a popular technique for improving communication complexity of stochastic first-order methods in distributed training of machine learning models. However, the existing works consider only with-replacement sampling of stochastic gradients. In contrast, it is well-known in practice and recently confirmed in theory that stochastic methods based on without-replacement sampling, e.g., Random Reshuffling (RR) method, perform better than ones that sample the gradients with-replacement. In this work, we close this gap in the literature and provide the first analysis of methods with gradient compression and without-replacement sampling. We first develop a distributed variant of random reshuffling with gradient compression (Q-RR) and show how to reduce the variance coming from gradient quantization through the use of control iterates. Next, to have a better fit for Federated Learning applications, we incorporate local computation and propose a variant of Q-RR called Q-NASTYA. Q-NASTYA uses local gradient steps and different local and global stepsizes. Next, we show how to reduce compression variance in this setting as well. Finally, we prove the convergence results for the proposed methods and outline several settings in which they improve upon existing algorithms.

---

<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="80px" src="https://burlachenkok.github.io/materials/MBZUAI-logo.png"/> </td>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="200px" src="https://burlachenkok.github.io/materials/princeton-university-logo.svg"/> </td>
</tr>
</table>