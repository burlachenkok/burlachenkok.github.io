---
layout: post
title: Personalized FL with Communication Compression.
published: true
---

The new paper [Personalized Federated Learning with Communication Compression](https://arxiv.org/abs/2209.05148) has been outed.

---

Our paper "Personalized Federated Learning with Communication Compression" has been out. The arXiv link for the paper: [https://arxiv.org/abs/2209.05148](https://arxiv.org/abs/2209.05148).

I was glad to work with my peers [El Houcine Bergou](https://zhizeli.github.io/) from [Mohammed VI Polytechnic University](https://www.um6p.ma/index.php/en/vision), [Aritra Dutta](http://www.aritradutta.com/) from [University of Southern Denmark](https://www.sdu.dk/en), [Peter Richtarik](https://richtarik.org/) from [King Abdullah University of Science and Technology](https://cemse.kaust.edu.sa/).

----

# Federated Learning

The limited amount of data for training big models for Machine Learning can leads to poor machine learning models or makes even training impossible if the high statistical variance of the obtained models is the key problem. On another side, the proliferation of mobile phones, wearable devices, tablets, and smart home devices comes with an increase in the volume of data captured and stored on them. This data contains a wealth of potentially useful information to the owners of these devices if appropriate machine learning models could be trained on the heterogeneous data stored on such devices. The traditional approach involves moving the relevant data to a data center where centralized machine learning techniques can be efficiently applied.  However, applying such an approach in practice leads to several issues: (a) Many device users are increasingly sensitive to privacy concerns and prefer their data to never leave their devices; (b) Moving data from their place of origin to a centralized location is very inefficient in terms of energy and time; (c) Data from different devices have different underlying distributions.

Federated learning (FL) ([research.google/pubs/pub45648](https://research.google/pubs/pub45648/), [arXiv:1912.04977](https://arxiv.org/abs/1912.04977), [arXiv:1908.07873](https://arxiv.org/abs/1908.07873)) has emerged as an interdisciplinary field focused on addressing these issues by training machine learning models directly on edge devices or organizations. In contrast to training traditional machine learning (ML) models in data centers, Federated Learning trains ML models over local datasets contained on resource-constrained heterogeneous edge devices.

---

# Our work

Existing FL algorithms aim to learn a single global model for all participating devices, which may not be helpful to all devices participating in the training due to the heterogeneity of the data across 
the devices. Recently, [Hanzely and Richtarik (2020)](https://arxiv.org/abs/2002.05516) proposed a new formulation for training personalized FL models aimed at balancing the trade-off between the traditional global model and the local models that could be trained by individual devices using their private data only. They derived a new algorithm, called [Loopless Gradient Descent (L2GD)](https://arxiv.org/abs/2002.05516), to solve it and showed that this algorithm leads to improved communication complexity guarantees in regimes when more personalization is required. 
In this paper, we equip their L2GD algorithm with a bidirectional compression mechanism to further reduce the communication bottleneck between the local devices and the server. 
Unlike other compression-based algorithms used in the FL-setting, our compressed L2GD algorithm operates on a probabilistic communication protocol, where communication does not happen on a fixed schedule. Our compressed L2GD algorithm maintains a similar convergence rate as vanilla SGD without compression.
To empirically validate the efficiency of our algorithm, we perform diverse numerical experiments and demonstrated the benefits of using our algorithm during training modern Deep Learning models used in Image Processing tasks: [DenseNet](https://arxiv.org/abs/1608.06993), [MobileNet](https://arxiv.org/abs/1704.04861), [ResNet](https://arxiv.org/abs/1512.03385). We include experiments with Logistic Regression the model which is widely used in Statistics, Optimization, and ML for training shallow models when the modeling effort is focused on feature design rather than creating complex function classes for supervised Machine Learning tasks. All our algorithms are equipped with the theory for convex and non-convex cases for finite sum minimization problems that include solving the Empirical Risk Minimization (ERM) problem in ML.

---

<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="80px" src="https://burlachenkok.github.io/materials/UM6P-logo.png"/> </td>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="80px" src="https://burlachenkok.github.io/materials/SDU-logo.png"/> </td>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="85px" src="https://burlachenkok.github.io/materials/KAUST-logo.png"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="85px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.png"/> </td>
</tr>
</table>
