---
layout: post
title: Unlocking FedNL on arXiv
published: true
---


The paper **[Unlocking FedNL: Self-Contained Compute-Optimized Implementation](https://arxiv.org/abs/2410.08760)** has been published on arXiv: [arXiv:2410.08760](https://arxiv.org/abs/2410.08760).



---

Existing work on Federated Newton Learning (FedNL) by **[Mher Safaryan](https://scholar.google.com/citations?user=dJNwgT8AAAAJ)**, **[Rustem Islamov](https://rustem-islamov.github.io/)**, **[Xun Qian](https://qianxunk.github.io/)**, and **[Peter Richtárik](https://richtarik.org/)** was presented at the **[39th International Conference on Machine Learning (ICML 2022)](https://icml.cc/virtual/2022/spotlight/17084)**. 

In the presented research, **[Konstantin Burlachenko](https://burlachenkok.github.io/)** and **[Peter Richtárik](https://richtarik.org/)** made significant strides in improving the practicality of the FedNL algorithm family, achieving a **1000x** improvement in the wall clock time over the original version, while also demonstrating superior performance compared to **[MOSEK](https://www.mosek.com/)**, **[Apache Spark](https://spark.apache.org/)**, **[Ray](https://www.ray.io/)**.

# Links

- **The arXiv preprint**: [https://arxiv.org/abs/2410.08760](https://arxiv.org/abs/2410.08760)
- **Podcast** generated via [NotebookLM](https://notebooklm.google/) in an entertaining format: [(i) Listen online here](https://www.podbean.com/eas/pb-zs34b-16d2942) and [(ii) Download offline here](https://burlachenkok.github.io/podcasts/u-fednl-before-rebuttal.mp3).


# Abstract

Federated Learning (FL) is an emerging paradigm that enables intelligent agents to collaboratively train Machine Learning (ML) models in a distributed manner, eliminating the need for sharing their local data. The recent work ([arXiv:2106.02969](https://arxiv.org/abs/2106.02969)) introduces a family of Federated Newton Learn (FedNL) algorithms, marking a significant step towards applying second-order methods to FL and large-scale optimization. However, the reference FedNL prototype exhibits three serious practical drawbacks: (i) It requires 4.8 hours to launch a single experiment in a sever-grade workstation; (ii) The prototype only simulates multi-node setting; (iii) Prototype integration into resource-constrained applications is challenging. To bridge the gap between theory and practice, we present a self-contained implementation of FedNL, FedNL-LS, and FedNL-PP for single-node and multi-node settings. Our work resolves the aforementioned issues and reduces the wall clock time by x1000. With this FedNL outperforms alternatives for training logistic regression in a single-node - CVXPY ([arXiv:1603.00943](https://arxiv.org/abs/1603.00943)), and in a multi-node - Apache Spark ([arXiv:1505.06807](https://arxiv.org/abs/1505.06807)), Ray/Scikit-Learn ([arXiv:1712.05889](http://arxiv.org/abs/1712.05889)). Finally, we propose two practical-orientated compressors for FedNL - adaptive TopLEK and cache-aware RandSeqK, which fulfill the theory of FedNL.

----

# Results

**1. Compute Effectiveness.** We addressed the challenge of executing computationally intensive multi-node simulations, achieving a remarkable **x1000** improvement in wall-clock time in the same hardware.

<table style="border-style: solid; width: 100%; border-collapse:collapse; border:1px solid">
  <caption>Table 1: Single-node simulation, n=142, FedNL(B), r=1000, λ=0.001, α - option 2, FP64, 24 cores@3.3 GHz.</caption>
  <thead>
    <tr style="border: 1px solid black;">
      <th style="border: 1px solid black;">Client Compression</th>
      <th style="border: 1px solid black;">$$\|\nabla f(x^{last})\|$$</th>
      <th style="border: 1px solid black;">Total Time (seconds)</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border: 1px solid black;">
      <td style="background-color: #CCFFCC;">1. RandK[K=8d] (We)</td>
      <td>$$3.00 \cdot 10^{-18}$$</td>
      <td>18.84</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>2. RandK[k=8d] (Base)</td>
      <td>$$3.00 \cdot 10^{-18}$$</td>
      <td>17,510.00</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td style="background-color: #CCFFCC;">3. TopK[K=8d] (We)</td>
      <td>$$2.80 \cdot 10^{-18}$$</td>
      <td>18.72</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>4. TopK[k=8d] (Base)</td>
      <td>$$2.80 \cdot 10^{-18}$$</td>
      <td>19,770.00</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td style="background-color: #CCFFCC;">5. RandSeqK[K=8d] (We)</td>
      <td> $$3.19 \cdot 10^{-18}$$ </td>
      <td>16.70</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td style="background-color: #CCFFCC;">6. TopLEK[K=8d] (We)</td>
      <td> $$3.45 \cdot 10^{-18}$$ </td>
      <td>18.48</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td style="background-color: #CCFFCC;">7. Natural (We)</td>
      <td>$$3.10 \cdot 10^{-18}$$</td>
      <td>27.02</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td style="background-color: #CCFFCC;">8. Ident (We)</td>
      <td>$$2.46 \cdot 10^{-18}$$</td>
      <td>24.12</td>
    </tr>
  </tbody>
</table>


**2. Self-Contained Design.** Our implementation facilitates seamless integration into resource-constrained systems:
- No library dependencies. Sole reliance on OS interfaces and some C++ Runtime elements
- Supports both single-node simulation and real multi-node execution
- Compatible with Linux, macOS, and Windows OS
- Buildable with MSVC (minimum 19.30), GNU GCC/G++ (minimum 11.4), LLVM CLANG (minimum 10.0)
- Tested on various CPU architectures (AMD64/x86_64, ARM v7, ARM64 v8, PowerPC PPC64LE, RISC-V 64, IBM Z Series)
- Explicit (optional) utilization of processor supplementary instruction sets: SSE2, AVX2, AVX-512, ARM Neon
- Modular design for handling complexity and ensuring code quality
- Support for creating oracles for optimization problems using NVIDIA CUDA (Compute Capability 7.0 to 9.0)
- Implementation can be utilized as native OS executable binaries, dynamic libraries, static libraries, and extension modules for languages supported by [SWIG](https://www.swig.org/).

**3/4. Two Practical Refinements of Existing Compressors.** We introduced an extension of the TopK compression mechanism, termed Top-LEK, which performs adaptive compression based on theoretical limits. Additionally, we proposed a cache-aware version of the RandK sparsification compressor, named RandSeqK.

**5. Outpefrom best-practice solutions.** Our implementation significantly outperforms solvers from [CVXPY](https://www.cvxpy.org/) capable of training logistic regression in a single-node scenario including commercial [MOSEK](https://www.mosek.com/). Below is the initialization and solve time, for extra metrics see Appendix F.

<table style="border-style: solid; width: 100%; border-collapse:collapse; border:1px solid">
  <caption>Table 2: Single-node simulation, n=142, FedNL-LS (B), FP64, 24 cores@3.3 GHz.</caption>
  <thead>
    <tr style="border: 1px solid black;">
      <th style="border: 1px solid black;">Solver</th>
      <th style="border: 1px solid black;">W8A <br> $$d=301,n_i=350$$</th>
      <th style="border: 1px solid black;">A9A <br> $$d=124,n_i=229$$</th>
      <th style="border: 1px solid black;">Phishing <br> $$d=69,n_i=77$$</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border: 1px solid black;">
      <td colspan="4" style="text-align:center;"><strong>Initialization Time (seconds)</strong></td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>CVXPY</td>
      <td>+2.54</td>
      <td>+2.33</td>
      <td>+2.28</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>FedNL</td>
      <td>+0.939</td>
      <td>+0.196</td>
      <td>+0.081</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td colspan="4" style="text-align:center;"><strong>Solving Time (seconds)</strong></td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>CLARABEL</td>
      <td>19.24</td>
      <td>10.83</td>
      <td>2.50</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>ECOS</td>
      <td>22.22</td>
      <td>8.02</td>
      <td>2.55</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>ECOS-BB</td>
      <td>22.00</td>
      <td>8.00</td>
      <td>2.12</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>SCS</td>
      <td>31.14</td>
      <td>19.36</td>
      <td>4.57</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>MOSEK</td>
      <td>16.90</td>
      <td>9.59</td>
      <td>3.55</td>
    </tr>
    <tr style="background-color:#CCFFCC;border: 1px solid black;">
      <td>FedNL-LS/RandK[k=8d]</td>
      <td>4.35</td>
      <td>0.34</td>
      <td>0.12</td>
    </tr>
    <tr style="background-color: #CCFFCC;border: 1px solid black;">
      <td>FedNL-LS/RandSeqK[k=8d]</td>
      <td>3.34</td>
      <td>0.29</td>
      <td>0.06</td>
    </tr>
    <tr style="background-color: #CCFFCC;border: 1px solid black;">
      <td>FedNL-LS/TopK[k=8d]</td>
      <td>4.49</td>
      <td>0.46</td>
      <td>0.10</td>
    </tr>
    <tr style="background-color: #CCFFCC;border: 1px solid black;">
      <td>FedNL-LS/TopLEK[k=8d]</td>
      <td>4.79</td>
      <td>0.34</td>
      <td>0.61</td>
    </tr>
    <tr style="background-color: #CCFFCC;border: 1px solid black;">
      <td>FedNL-LS/Natural</td>
      <td>3.13</td>
      <td>0.17</td>
      <td>0.08</td>
    </tr>
    <tr style="background-color: #CCFFCC;border: 1px solid black;">
      <td>FedNL-LS/Identical</td>
      <td>0.63</td>
      <td>0.09</td>
      <td>0.06</td>
    </tr>
  </tbody>
</table>

Our implementation outperforms solvers from [Apache Spark](https://spark.apache.org/) and [Ray](https://www.ray.io/) in a multi-node (number of nodes is 50) in the logistic regression benchmarks.

<table style="border-style: solid; width: 100%; border-collapse:collapse; border:1px solid">
  <caption>Table 3: Multi-node setting, n=50 clients, 1 master, FP64, 1 CPU core/node.</caption>
  <thead>
    <tr style="border: 1px solid black;">
      <th style="border: 1px solid black;">Solution</th>
      <th style="border: 1px solid black;">W8A <br> $$d=301,n_i=994$$</th>
      <th style="border: 1px solid black;">A9A <br> $$d=124,n_i=651$$</th>
      <th style="border: 1px solid black;">Phishing <br> $$d=69,n_i=221$$</th>
    </tr>
  </thead>
  <tbody>
    <tr style="border: 1px solid black;">
      <td colspan="4" style="text-align:center;"><strong>Initialization Time (seconds)</strong></td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>Ray</td>
      <td colspan="3" style="text-align:center;">+52.0</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>Spark</td>
      <td colspan="3" style="text-align:center;">+25.82</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>FedNL</td>
      <td colspan="3" style="text-align:center;">+1.1</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td colspan="4" style="text-align:center;"><strong>Solving Time (seconds)</strong></td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>Ray</td>
      <td>116.17</td>
      <td>28.13</td>
      <td>11.54</td>
    </tr>
    <tr style="border: 1px solid black;">
      <td>Spark</td>
      <td>36.65</td>
      <td>33.59</td>
      <td>33.14</td>
    </tr>
    <tr style="background-color: #CCFFCC;border-style:solid;">
      <td>FedNL/RandK[k=8d]</td>
      <td>12.6</td>
      <td>4.52</td>
      <td>0.21</td>
    </tr>
    <tr style="background-color: #CCFFCC;border-style:solid;">
      <td>FedNL/RandSeqK[k=8d]</td>
      <td>12.56</td>
      <td>5.10</td>
      <td>0.14</td>
    </tr>
    <tr style="background-color: #CCFFCC;border-style:solid;">
      <td>FedNL/TopK[k=8d]</td>
      <td>12.20</td>
      <td>5.79</td>
      <td>5.23</td>
    </tr>
    <tr style="background-color: #CCFFCC;border-style:solid;">
      <td>FedNL/TopLEK[k=8d]</td>
      <td>15.11</td>
      <td>3.26</td>
      <td>0.82</td>
    </tr>
    <tr style="background-color: #CCFFCC;border-style:solid;">
      <td>FedNL/Natural</td>
      <td>5.75</td>
      <td>1.56</td>
      <td>0.14</td>
    </tr>
  </tbody>
</table>


**6. First Robust Practical Implementation.** We hold respect for contributors to the diverse landscape of training runtimes for FL. However, to the best of our knowledge, our implementation represents the first *robust* practical solution for training (strongly) convex objectives in Federated Learning settings (see Section 9.4 of the paper).

# Broader Impact

**The Role of Theory in Practice.** The interplay between theory and practice remains a landscape still being explored. In our work, we explicitly identify the theoretical elements that facilitated our efforts to bridge the gap between theoretical concepts and practical implementation (see Appendix K.2).

**Translating Theory into Practice.** Our work serves as a guiding beacon for researchers navigating the complex process of translating theoretical algorithms into impactful implementations across various domains of Machine Learning. Even theoretically optimal algorithms may underperform in practical benchmarks that assess the actual time and memory. It's often due to significant hidden implementation constants in layered designs. We highlight a comprehensive set of considerations that must be considered to successfully implement a scientific algorithm without sacrificing performance.

**The Significance of Alternative Languages in ML Research.** Our work emphasizes the multifaceted considerations involved in improving actual wall clock time. It challenges the predominant Python-centric design philosophy in Machine Learning and underscores the significance of considering alternative languages when prioritizing computational and memory efficiency.

----

# Postscriptum

Much like the bonus levels in the video game [Crash Bandicoot](https://en.m.wikipedia.org/wiki/Crash_Bandicoot) our current project required four essential components:

* (a) Careful analysis and identification of systematic runtime problems (*Discover the bonus level*)
* (b) Elimination of a large number of minor approximations or errors (*Observe the collection of small apples in the bonus level*)
* (c) A cascade of meticulous modifications and measurements (*Collect a large number of small apples in the bonus level*)
* (d) Perseverance (*Avoid traps and navigate carefully in the bonus level with a limited visible environment*)

---

<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="95px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="155px" src="https://burlachenkok.github.io/materials/crash-bandicoot-web.jpg"/> </td>
</tr>
</table>
