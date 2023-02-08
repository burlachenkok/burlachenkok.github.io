---
layout: post
title: Federated Learning with Regularized Client Participation.
published: true
---

The new paper [Federated Learning with Regularized Client Participation](https://arxiv.org/abs/2302.03662) has been outed.

---

I was glad to work my peers [Grigory Malinovsky](https://k3nfalt.github.io/), prof. [Samuel Horvath](https://lukangsun.github.io/), and prof. [Peter Richtarik](https://richtarik.org/) from [King Abdullah University of Science and Technology](https://cemse.kaust.edu.sa/) on the paper **"Federated Learning with Regularized Client Participation"**.

The arXiv link for the paper: [https://arxiv.org/abs/2302.03662](https://arxiv.org/abs/2302.03662). 

During numerical experiments for that paper, we heavily exploited **FL_PyTorch** - an advanced research simulator for Federated Learning ([https://dl.acm.org/doi/10.1145/3488659.3493775](https://dl.acm.org/doi/10.1145/3488659.3493775), [FL_PyTorch presentation at rising starts in AI Symposium](https://burlachenkok.github.io/FL_PyTorch-presentation-at-rising-starts-in-AI-Symposium/)).

# Abstract

Federated Learning (FL) is a distributed machine learning approach where multiple clients work together to solve a machine learning task. One of the key challenges in FL is the issue of partial participation, which occurs when a large number of clients are involved in the training process. The traditional method to address this problem is randomly selecting a subset of clients at each communication round. 

In our research, we propose a new technique and design a novel regularized client participation scheme. Under this scheme, each client joins the learning process every $$R$$ communication rounds, which we refer to as a meta epoch.
We have found that this participation scheme leads to a reduction in the variance caused by client sampling. Combined with the popular $$\texttt{FedAvg}$$ algorithm (McMahan et al., 2017), it results in superior rates under standard assumptions. For instance, the optimization term in our main convergence bound decreases linearly with the product of the number of communication rounds and the size of the local dataset of each client, and the statistical term scales with step size quadratically instead of linearly (the case for client sampling with replacement), leading to better convergence rate $$\mathcal{O}(1/T^2)$$ compared to $$\mathcal{O}(1/T)$$, where $$T$$ is the total number of communication rounds. 

Furthermore, our results permit arbitrary client availability as long as each client is available for training once per each meta epoch.

---

<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.png"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.png"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/MBZUAI_Logo.png"/> </td> 
</tr>
</table>
