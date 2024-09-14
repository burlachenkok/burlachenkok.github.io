---
layout: post
title: Unlocking FedNL at Virtual Radio Studio
published: true
---

*Unlocking FedNL: Self-Contained Compute-Optimized Implementation** at Virtual Radio Studio

---




I am excited to share my latest experience using a Personalized AI research assistant from Google -  [NotebookLM](https://notebooklm.google/). 


I fed our recent research paper *Unlocking FedNL: Self-Contained Compute-Optimized Implementation* and generated a highly engaging and informative radio podcast. The podcast captures the core message of the work and delivers it in an entertaining format.

**How to Listen:**
* Online: [https://www.podbean.com/eas/pb-zs34b-16d2942](https://www.podbean.com/eas/pb-zs34b-16d2942)
* Offline: [u-fednl-before-rebuttal.mp3](https://burlachenkok.github.io/audio/u-fednl-before-rebuttal.mp3)


Currently, the paper is undergoing peer review and is not publicly available. 

For more details, check out the description [Unlocking FedNL at the Rising Stars AI Symposium in February 2024](https://burlachenkok.github.io/Unlocking-FedNL-at-KAUST-AI-Simposium/).

---

**Context.** 

Federated Learning (FL) is an innovative paradigm that allows a large number of intelligent agents to collaboratively train machine learning (ML) models.
A recent paper by Safaryan et al. (2021) introduced the [FedNL (Federated Newton Learn)](https://arxiv.org/abs/2106.02969) algorithm, marking a significant milestone 
In applying second-order optimization methods to FL and large-scale optimization. 

The reference [FedNL (Federated Newton Learn)](https://arxiv.org/abs/2106.02969) prototype faces three notable challenges:

* It takes approximately 4.8 hours to run a single experiment on a server-grade workstation.

* The prototype supports only single-node execution.

* The FedNL algorithms were implemented in [Python](https://www.python.org/), making integration into resource-constrained ML applications difficult.

Our work addresses these challenges as follows:

* A) We reduced the wall-clock time by a factor of 1,000 for single-node simulations on the same hardware and on the same configuration.
* B) The implementation does not rely on third-party computation or data-processing frameworks.
* C) We developed two practical compressors: one is Problem Adaptive and the other is CPU Cache-aware.
* D) Finally, FedNL outperforms existing solutions in both single-node and multi-node settings:

In single-node scenarios, it outperforms [CVXPY](https://www.cvxpy.org/) ([Diamond & Boyd, 2016](https://arxiv.org/abs/1603.00943)).
In multi-node scenarios, it surpasses [Apache Spark](https://spark.apache.org/) ([Meng et al., 2016](https://www.jmlr.org/papers/volume17/15-237/15-237.pdf)), [Rays/Scikit-Learn](https://www.ray.io/) ([Moritz et al., 2018](https://www.usenix.org/system/files/osdi18-moritz.pdf)).
