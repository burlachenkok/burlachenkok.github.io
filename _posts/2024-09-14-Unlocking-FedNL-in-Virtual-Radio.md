---
layout: post
title: Unlocking FedNL in Virtual Radio Studio
published: true
---

*Unlocking FedNL Self-Contained Compute-Optimized Implementation (Research from KAUST)* in Virtual Radio Studio

---

I am excited to share my latest experience using a Personalized AI research assistant from Google -  [NotebookLM](https://notebooklm.google/).
I fed one of my recent research paper created jointly with my peer (and advisor) [P.Richtárik](https://richtarik.org/) *Unlocking FedNL: Self-Contained Compute-Optimized Implementation* and generated a highly engaging and informative radio podcast from [NotebookLM](https://notebooklm.google/). Generated audio:

* Online: [https://www.podbean.com/eas/pb-zs34b-16d2942](https://www.podbean.com/eas/pb-zs34b-16d2942)
* Offline: [u-fednl-before-rebuttal.mp3](https://burlachenkok.github.io/podcasts/u-fednl-before-rebuttal.mp3)

The podcast captures the core message of the work and delivers it in an entertaining format. Currently, the paper is undergoing peer review and is not publicly available.


---

# Abstract

Federated Learning (FL) is an innovative paradigm that allows a large number of intelligent agents to collaboratively train machine learning (ML) models.
A recent paper by [Safaryan](https://scholar.google.com/citations?user=dJNwgT8AAAAJ&hl=en),[Islamov](https://rustem-islamov.github.io/),[Qian](https://qianxunk.github.io/),[Richtárik](https://richtarik.org/) (2021) introduced the [FedNL (Federated Newton Learn)](https://arxiv.org/abs/2106.02969) algorithm, marking a significant milestone 
In applying second-order optimization methods to FL and large-scale optimization. The reference [FedNL (Federated Newton Learn)](https://arxiv.org/abs/2106.02969) prototype faces three notable challenges:

* It takes approximately 4.8 hours to run a single experiment on a server-grade workstation.

* The prototype supports only single-node execution.

* The FedNL algorithms were implemented in [Python](https://www.python.org/), making integration into resource-constrained ML applications difficult.

# Contributions

Our work addresses these challenges as follows:

* We reduced the wall-clock time by a factor of 1000 for single-node simulations on the same hardware and on the same configuration
* The implementation does not rely on third-party computation or data-processing frameworks
* We developed two practical compressors: one is Problem Adaptive and the other is CPU Cache-aware
* Finally, FedNL outperforms existing solutions in both single-node and multi-node settings

# Results

* In single-node scenarios, it outperforms all available solvers which can solve logistic regression model from [CVXPY](https://www.cvxpy.org/) ([Diamond & Boyd, 2016](https://arxiv.org/abs/1603.00943)).
* In multi-node scenarios, it surpasses [Apache Spark](https://spark.apache.org/) ([Meng et al., 2016](https://www.jmlr.org/papers/volume17/15-237/15-237.pdf))
* Also in multi-node scenarios, it surpasses [Rays/Scikit-Learn](https://www.ray.io/) ([Moritz et al., 2018](https://www.usenix.org/system/files/osdi18-moritz.pdf)).

---

<table style="text-align:center;">
<tr>
<table>
<tr>
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
</tr>
</table>
