---
layout: post
title: Personalized FL with Communication Compression at TMLR
published: true
---

The paper [Personalized Federated Learning with Communication Compression](https://openreview.net/forum?id=dZugyhbNFY) was accepted by the [Transactions on Machine Learning Research](https://jmlr.csail.mit.edu/tmlr/index.html).

---


The paper *"Personalized Federated Learning with Communication Compression"* was accepted by the [Transactions on Machine Learning Research (TMLR)](https://jmlr.csail.mit.edu/tmlr/index.html). TMLR is a venue for the dissemination of machine learning research which emphasizes technical correctness over subjective significance.

I was glad to work with my peers:
* [Peter Richtárik](https://richtarik.org/) from [King Abdullah University of Science and Technology, KSA](https://cemse.kaust.edu.sa/)
* [Aritra Dutta](http://www.aritradutta.com/) from [Artificial Intelligence Initiative University of Central Florida, USA](https://ai.ucf.edu/)
* [El Houcine Bergou](https://ehbergou.github.io) from [Mohammed VI Polytechnic University, Morocco](https://www.um6p.ma/index.php/en/vision)

---

Link to the paper: [https://openreview.net/forum?id=dZugyhbNFY](https://openreview.net/forum?id=dZugyhbNFY)

Accepted papers to [TMLR](https://jmlr.org/tmlr/) can be browsed directly from [OpenReview](https://openreview.net/group?id=TMLR). 

---

# Our Work

The limited amount of data for training big models for Machine Learning can lead to poor machine learning models, or make even training impossible. Federated learning (FL) ([research.google/pubs/pub45648](https://research.google/pubs/pub45648/), 
[arXiv:1912.04977](https://arxiv.org/abs/1912.04977), [arXiv:1908.07873](https://arxiv.org/abs/1908.07873)) has emerged as an interdisciplinary field focused on addressing these issues by training machine learning models directly on edge devices or organizations. In contrast to training traditional machine learning (ML) models in data centers, Federated Learning trains ML models over local datasets contained on resource-constrained heterogeneous edge devices.

Existing FL algorithms mainly aim to learn a single global model for all participating devices. However, it may not be helpful to all devices participating in the training due to the heterogeneity of the data across the devices. Recently, [Hanzely and Richtárik (2020)](https://arxiv.org/abs/2002.05516) proposed a new formulation for training personalized FL models aimed at 
balancing the trade-off between the traditional global model and the local models that could be trained by individual devices using their private data only. They derived a new algorithm, called [Loopless Gradient Descent (L2GD)](https://arxiv.org/abs/2002.05516), to solve it and showed that this algorithm leads to improved communication complexity guarantees.

In our paper, we equipped their L2GD algorithm with a bidirectional compression mechanism to further reduce the communication bottleneck between the local devices and the server. Unlike other compression-based algorithms used in the FL setting, our <span style="color:rgb(74,126,104)">Compressed L2GD</span> algorithm operates on a probabilistic communication protocol, where communication does not happen on a fixed schedule.

Our <span style="color:rgb(74,126,104)">Compressed L2GD</span> algorithm maintains a similar convergence rate as vanilla SGD without compression. To validate the efficiency of our algorithm, we performed diverse numerical experiments and demonstrated the benefits of using our algorithm during training modern Deep Learning models used in Image Processing tasks:

* [DenseNet-121](https://arxiv.org/abs/1608.06993)
* [MobileNet](https://arxiv.org/abs/1704.04861)
* [ResNet-18/56](https://arxiv.org/abs/1512.03385)

We included experiments with Logistic Regression the model that is widely used in Statistics, Optimization, and Machine Learning (ML) for training shallow models when the modeling effort is focused on feature design rather than creating complex function classes for supervised ML tasks.

All our algorithms are equipped with the theory for convex and non-convex cases for finite sum minimization problems, including solving the Empirical Risk Minimization (ERM) problem in ML.

---


<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="85px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="190px" src="https://burlachenkok.github.io/materials/ucf-logo-2022.svg"/> </td>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="75px" src="https://burlachenkok.github.io/materials/UM6P-logo.png"/> </td>
</tr>
</table>
