---
layout: post
title: Unlocking FedNL Self-Contained Compute-Optimized Implementation
published: false
---


Paper [Unlocking FedNL Self-Contained Compute-Optimized Implementation](https://arxiv.org/abs/2405.14852) has been published in arXiv.

---

The Federated Newton Learn (FedNL) per se ([arxiv:2106.02969](https://arxiv.org/abs/2106.02969)) has been published and presented in [39th International Conference on Machine Learning](https://icml.cc/virtual/2022/spotlight/17084). In the present multi-faceted research [Konstantin Burlachenko](https://burlachenkok.github.io/) and [Prof.Peter Richtárik](https://richtarik.org/) discovered and made various steps to make the Federated Newton Learn Algorithm family more practical. 

We provide a comparison with Apache Spark and Ray (platforms from Data-Intensive Computing). These platforms provide convergence guarantees in utilized solvers. We strive for more broad applicability of Federated Learning in society. To achieve this Applications should have the ability to use Federated Learning without human intervention almost completely. 

> For example you are operating with a web browser right now and you tune nothing in loaded extensions algorithms.

If this is a goal, then our work can not be compared virtually with all (open-source) runtimes for Federated Learning due to the absence of robust convergence guarantees in their solvers.

---

# Links

* The arXiv preprint: Unlocking FedNL: Self-Contained Compute-Optimized Implementation
* Radio podcast generated via [Google NotebookLM](https://notebooklm.google/) in an entertaining format:
    * Online: [https://www.podbean.com/eas/pb-zs34b-16d2942](https://www.podbean.com/eas/pb-zs34b-16d2942)
    * Offline: [https://burlachenkok.github.io/podcasts/u-fednl-before-rebuttal.mp3](https://burlachenkok.github.io/podcasts/u-fednl-before-rebuttal.mp3)

The research reported in this publication was supported by funding from [King Abdullah University of Science and Technology](https://www.kaust.edu.sa/en/) (see Appendix M).

---

# Abstract

Federated Learning (FL) is an emerging paradigm that enables intelligent agents to collaboratively train Machine Learning (ML) models in a distributed manner, eliminating the need for sharing their local data. The recent work ([arXiv:2106.02969](https://arxiv.org/abs/2106.02969)) introduces a family of Federated Newton Learn (FedNL) algorithms, marking a significant step towards applying second-order methods to FL and large-scale optimization. However, the reference FedNL prototype exhibits three serious practical drawbacks: (i) It requires 4.8 hours to launch a single experiment in a sever-grade workstation; (ii) The prototype only simulates multi-node setting; (iii) Prototype integration into resource-constrained applications is challenging. To bridge the gap between theory and practice, we present a self-contained implementation of FedNL, FedNL-LS, and FedNL-PP for single-node and multi-node settings. Our work resolves the aforementioned issues and reduces the wall clock time by x1000. With this FedNL outperforms alternatives for training logistic regression in a single-node - CVXPY ([arXiv:1603.00943](https://arxiv.org/abs/1603.00943)), and in a multi-node - Apache Spark ([arXiv:1505.06807](https://arxiv.org/abs/1505.06807)), Ray/Scikit-Learn ([arXiv:1712.05889](http://arxiv.org/abs/1712.05889)). Finally, we propose two practical-orientated compressors for FedNL - adaptive TopLEK and cache-aware RandSeqK, which fulfill the theory of FedNL.

---

# Results

**A. Compute Effectiveness**. We addressed the challenge of executing computationally intensive multi-node simulations for FedNL on a single workstation, achieving a remarkable x1000 improvement in wall-clock time in the same hardware. 

<table style="width:100%">
<tr>
 <th style="border-style:solid;"> Client Compression</th>
 <th style="border-style:solid;">$$\nabla f(x^{last})$$ </th>
 <th style="border-style:solid;">Total Time (seconds)</th>
 </tr>

 <tr style="background-color: #CCFFCC;border-style:solid;">
 <td>1. RandK[K=8d] (We)</td>
 <td>$$3 \cdot 10^{-18}$$</td>
 <td>18.84</td>
 </tr>

 <tr style="border-style:solid;">
 <td>2. RandK[K=8d] (Base)</td>
 <td>$$3 \cdot 10^{-18}$$</td>
 <td>17 510.00</td>
 </tr>

 <tr style="background-color: #CCFFCC;border-style:solid;">
 <td>3. TopK[K=8d] (We)</td>
 <td>$$2.80 \cdot 10^{-18}$$</td>
 <td>18.72</td>
 </tr>

 <tr style="border-style:solid;">
 <td>4. TopK[K=8d] (Base)</td>
 <td>$$2.80 \cdot 10^{-18}$$</td>
 <td>19 770.00</td>
 </tr>

 <tr style="background-color: #CCFFCC;border-style:solid;">
 <td>5. RandSeqK[K=8d] (We)</td>
 <td>$$3.19 \cdot 10^{-18}$$</td>
 <td>16.70</td>
 </tr>

 <tr style="background-color: #CCFFCC;border-style:solid;">
 <td>6. TopLEK[K=8d] (We)</td>
 <td>$$3.45 \cdot 10^{-18}$$</td>
 <td>18.48</td>
 </tr>

 <tr style="background-color: #CCFFCC;border-style:solid;">
 <td>7. Natural (We)</td>
 <td>$$3.45 \cdot 10^{-18}$$</td>
 <td>27.02</td>
 </tr>

 <tr style="background-color: #CCFFCC;border-style:solid;">
 <td>8. Ident (We)</td>
 <td>$$2.46 \cdot 10^{-18}$$</td>
 <td>24.12</td>
 </tr>
</table>

**B. Self-Contained Design.** Our design facilitates seamless integration into resource-constrained systems and supports extensibility for future research:

* Our design eliminates the need for library dependencies management completely
* Our solution relies solely only on OS interfaces and elements of some elements of the C++ Runtime
* Support single-node and multi-node settings with TCP/IPv4 and TCP/IPv6 communication
* Compatible with Linux, macOS, and Windows
* The supported toolchains for building our code are: (i) Visual Studio/MSVC (minimum: VS2022, MSVC 19.30); (ii) GNU GCC/G++ (minimum: 11.4); (iii) LLVM CLANG (minimum: 10.0)
* Has been tested on: AMD64/x86_64, ARM v7, ARM64 v8, PowerPC PPC64LE, RISC-V 64, IBM Z Series Architecture (S390X)
* We provide step-by-step guidelines and handle complexity by modular design (during compile time)
* Addressing slow compilation and code quality by leveraging modern tools
* Project contains limited support for creating oracles for optimization problems using NVIDIA CUDA (from CUDA Compute Capability 7.0 to CUDA Compute Capability: 9.0) and utilities for numerical tests of constructed oracles
* Finally the implementation can be utilized: As native OS executable binary applications, as a native dynamic library, as static libraries, and as an extension module for other programming languages supported by [SWIG](https://www.swig.org/)

**C. Work contains Practical Refinements of Existing Compressors.** We introduced an extension of the TopK compression mechanism, termed Top-LEK. The core idea is to perform compression for TopK adaptively and compress as much as the theory allows, but not more. Also, we proposed a cache-aware version of the RandK sparsification compressor, named RandSeqK.

**D. Outperforms Apache Spark, Ray, and solvers from CVXPY (including MOSEK).** In a single-node setup, our implementation practically outperforms solvers encapsulated within CVXPY [11], including the commercial MOSEK [1] for solving logistic regression. In a multi-node setup, our implementation surpasses the performance of Apache Spark MLlib [37] and Ray/Scikit-Learn [38]. Our implementation has a smaller initialization time and smaller runtime.

**E. First Robust Practical Implementation.** To the best of our knowledge, our implementation is the first robust, practical implementation for training (strongly) convex objectives in Federated Learning settings (in a strong sense). See Section 9.4 of the paper for what we mean by that.

----

# Broader Impact

**I. The Role of the Theory in Practice.** I appreciate Prof.Stephen Boyd highlighting the fact that the interplay between theory and practice is not clear ([H20.ai, Future is Now - Panel, 4 Dec 2015, 16:10](https://youtu.be/2sSytdFG7yc?t=973)). And probably the full catalog of how theory interplay with practice is still in the process of discovering.  In our work, we explicitly stated which elements of theory helped us in constructing a bridge between theory and practice (see Appendix K.2).

**II. Significance of Alternative Languages for Machine Learning Research.** Our work emphasizes the multifaceted considerations involved in aiming to improve the actual wall clock time. Our work challenges the predominant Python-centric design philosophy in Machine Learning. It underscores the significance of considering alternative languages when prioritizing computational and memory efficiency.

**III. How To Transfer Theory into Practice.** Our work serves as a guiding beacon for researchers navigating the intricate path of translating theoretical algorithms into impactful implementations across diverse domains of Machine Learning. Even theoretically optimal algorithms may unperformed in practical benchmarks that measure time and memory due to large hidden implementation constants in layered designs. Our methodology highlights the (big) set of considerations that should be taken into mind if the research goal is to implement a good algorithm without compromising performance.

----

# Postscriptum

In the past, we gained improvement by factor x1000 in terms of communication memory during security preserving training, see our paper [Federated Learning is Better with Non-Homomorphic Encryption](https://dl.acm.org/doi/10.1145/3630048.3630182), Figure 6.  However, previous times to get improvement under HE/CKKS required us to completely change the methodology of utilized Cryptographic Tools - essentially to switch to classical ones and resolve (huge) problem (essentially inability to use any arithmetics) with special mathematical tools.

This time approach to get x1000 improvement was different. When I was a teenager I played in Crash Bandicoot. In this and similar games, there was a bonus level. This project aspect essentially required us 4 things:

* (a) Careful thinking and identifying collection of systematic problems in runtime (*Discover bonus level*)
* (b) Eliminating big amount of small resolvable mistakes (*Observe a big collection of small apples in bonus level*)
* (c) Cascade of careful modifications and measurements (*Working in bonus level*)
* (d) Perseverance (*Do not fall into the trap and perform movements in a bonus level with a limited observed environment*)

----


<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="95px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
</tr>

<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="95px" src="https://burlachenkok.github.io/materials/crash-bandicoot-web.jpg"/> </td> 
</tr>

</table>
