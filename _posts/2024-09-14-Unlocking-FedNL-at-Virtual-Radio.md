---
layout: post
title: Unlocking FedNL at Virtual Radio
published: true
---

**"Unlocking FedNL: Self-Contained Compute-Optimized Implementation"* at Virtual Radio.

---

I’m excited to share my latest experience using [NotebookLM](https://notebooklm.google/). Podcast: 
* [https://burlachenkok.podbean.com/e/unlocking-fednl-self-contained-compute-optimized-implementation/](https://burlachenkok.podbean.com/e/unlocking-fednl-self-contained-compute-optimized-implementation/)
* [record-mp3-copy](https://burlachenkok.github.io/audio/u-fednl-before-rebuttal.mp3)

I fed in research papers and generated a highly engaging and informative radio podcast. 

The podcast captures the core message of the work and delivers it in an entertaining format.

Currently, the paper is undergoing peer review and is not publicly available. For more details, check out [Unlocking FedNL at the Rising Stars AI Symposium in February 2024](https://burlachenkok.github.io/Unlocking-FedNL-at-KAUST-AI-Simposium/).



---

**Context.** 

Federated Learning (FL) is an innovative paradigm that allows a large number of intelligent agents to collaboratively train machine learning (ML) models.
A recent paper by Safaryan et al. (2021) introduced the [FedNL (Federated Newton Learn)](https://arxiv.org/abs/2106.02969) algorithm, marking a significant milestone 
in applying second-order optimization methods to FL and large-scale optimization. 

The reference FedNL prototype faces three notable challenges:

* It takes approximately 4.8 hours to run a single experiment on a server-grade workstation.

* The prototype supports only single-node execution.

* The FedNL algorithms were implemented in [Python](https://www.python.org/), making integration into resource-constrained ML applications difficult.

Our work addresses these challenges as follows:

* A) We reduced the wall-clock time by a factor of 1,000 for single-node simulations.
* B) The implementation does not rely on third-party computation or data-processing frameworks.
* C) We developed two practical compressors: one is Problem Adaptive and the other is CPU Cache-aware.
* D) Finally, FedNL outperforms existing solutions in both single-node and multi-node settings:

In single-node scenarios, it outperforms [CVXPY](https://www.cvxpy.org/) ([Diamond & Boyd, 2016](https://arxiv.org/abs/1603.00943)).
In multi-node scenarios, it surpasses [Apache Spark](https://spark.apache.org/) ([Meng et al., 2016](https://www.jmlr.org/papers/volume17/15-237/15-237.pdf)), [Rays/Scikit-Learn](https://www.ray.io/) ([Moritz et al., 2018](https://www.usenix.org/system/files/osdi18-moritz.pdf)).
