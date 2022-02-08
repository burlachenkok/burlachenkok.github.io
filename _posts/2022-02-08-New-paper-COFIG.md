---
layout: post
title: Faster rates for compressed federated learning with client-variance reduction
published: true
---

The new paper ["Faster rates for compressed federated learning with client-variance reduction"](https://arxiv.org/abs/2112.13097) has been out.

---

Our paper ["Faster rates for compressed federated learning with client-variance reduction"](https://arxiv.org/abs/2112.13097) has been out. I was glad to work with my peers [Haoyu Zhao](https://hyzhao.me/) from [Princeton University](https://www.princeton.edu/), [Zhize Li](https://zhizeli.github.io/), and prof. [Peter Richtarik](https://richtarik.org/) from [King Abdullah University of Science and Technology](https://cemse.kaust.edu.sa/).

We provide rigorous theory and a rich amount of practical experiments to highlight the benefits of our methods. In terms of practice, we are providing comparisons of several state-of-the-art optimization FL algorithms with theoretical and tunable parameters.

The provided experiments include distributed binary logistic regression with convex and nonconvex regularizer, and Image classification ResNet-18@CIFAR10 in a setting when a communication channel from master to the client can only work with one client per round.

Our [COFIG](https://arxiv.org/abs/2112.13097) algorithm has demonstrated in honest comparison excellent results.

The experimental part for that paper has been done in an advanced research simulator for Federated Learning called [FL_PyTorch](https://dl.acm.org/doi/10.1145/3488659.3493775) that is currently in process of Alpha testing.
