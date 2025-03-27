---
layout: post
title: On Making Three Projects Open-Source
published: true
---

On making BurTorch, uFedNL, and PermK/AES open-source.

---

Collaboration is key to advancing the fields, and we have opened three projects to future work with researchers, developers, and organizations who are interested in pushing the boundaries. Whether it is improving this implementation, contributing new ideas, or creating applications on top of these projects.  We welcome your involvement! Feel free to reach out, open an issue, or submit a pull request on GitHub.

Below is a brief overview of each project from now on available in GitHub:

- [https://github.com/burlachenkok/burtorch](https://github.com/burlachenkok/burtorch)
- [https://github.com/burlachenkok/ufednl](https://github.com/burlachenkok/ufednl)
- [https://github.com/burlachenkok/fl-with-nonhe](https://github.com/burlachenkok/fl-with-nonhe)

---


# BurTorch: Revisiting Training from First Principles by Coupling Autodiff, Math Optimization, and Systems

## BurTorch Abstract 

In this work, we introduce BurTorch, a compact high-performance framework designed to optimize Deep Learning (DL) training on single-node workstations 
through an exceptionally efficient CPU-based backpropagation ([Rumelhart et al., 1986](https://www.nature.com/articles/323533a0); [Linnainmaa, 1970](https://scholar.googleusercontent.com/scholar.bib?q=info:wRjDZKQ_NKYJ:scholar.google.com/&output=citation&scisdr=ClHdwmNeENKs6Xb1i_s:AFWwaeYAAAAAZ87zk_vuPijL7H0txyMVOwPA1wQ&scisig=AFWwaeYAAAAAZ87zk4D5Rjhb-wNl_c2IxQBTkcc&scisf=4&ct=citation&cd=-1&hl=ru)) implementation. Although modern DL frameworks rely on compiler-like optimizations internally, BurTorch takes a different path. It adopts a minimalist design and demonstrates that, 
in these circumstances, classical compiled programming languages can play a significant role in DL research. 
By eliminating the overhead of large frameworks and making efficient implementation choices, BurTorch achieves orders-of-magnitude improvements in performance and memory efficiency when 
computing the gradient of a function on a CPU. BurTorch features a compact codebase designed to achieve two key goals simultaneously. 
First, it provides a user experience similar to script-based programming environments. 
Second, it dramatically minimizes runtime overheads. In large DL frameworks, the primary source of memory overhead for relatively small computation graphs is due to feature-heavy implementations. 
We benchmarked BurTorch against widely used DL frameworks in their execution modes: 
[JAX (Bradbury et al., 2018)](https://github.com/jax-ml/jax), [PyTorch (Paszke et al., 2019)](https://proceedings.neurips.cc/paper/2019/hash/bdbca288fee7f92f2bfa9f7012727740-Abstract.html), [TensorFlow (Abadi et al., 2016)](https://arxiv.org/abs/1605.08695);
and several standalone libraries: [Autograd (Maclaurin et al., 2015)](https://github.com/HIPS/autograd), [Micrograd (Karpathy, 2020)](https://github.com/karpathy/micrograd), [Apple MLX (Hannun et al., 2023)](https://github.com/ml-explore).
For small compute graphs, BurTorch outperforms best-practice solutions by up to x2000 in runtime and reduces memory consumption by up to x3500. For a miniaturized [GPT-3 model (Brown et al., 2020)](https://arxiv.org/abs/2005.14165), 
BurTorch achieves up to a x20 speedup and reduces memory up to x80 compared to [PyTorch](https://proceedings.neurips.cc/paper/2019/hash/bdbca288fee7f92f2bfa9f7012727740-Abstract.html).

## BurTorch Links

- **The arXiv preprint**: [https://arxiv.org/abs/2503.13795](https://arxiv.org/abs/2503.13795)
- **The arXiv preprint in KAUST Library repository**: [https://repository.kaust.edu.sa/bitstreams/0997f91f-441a-4f16-9003-3e33e729134e/download](https://repository.kaust.edu.sa/bitstreams/0997f91f-441a-4f16-9003-3e33e729134e/download)
- **The GitHub repository**: [https://github.com/burlachenkok/burtorch](https://github.com/burlachenkok/burtorch)
- **Relative posts**: [https://burlachenkok.github.io/burtorch/](https://burlachenkok.github.io/burtorch/)

---

# Unlocking FedNL: Self-Contained Compute-Optimized Implementation


## uFedNL Abstract

Federated Learning (FL) is an emerging paradigm that enables intelligent agents to collaboratively train Machine Learning (ML) models in a distributed manner, eliminating the need for sharing their local data. The recent work ([arXiv:2106.02969](https://arxiv.org/abs/2106.02969)) introduces a family of Federated Newton Learn (FedNL) algorithms, marking a significant step toward applying second-order methods to FL and large-scale optimization. However, the reference FedNL prototype exhibits three serious practical drawbacks: (i) It requires 4.8 hours to launch a single experiment in a sever-grade workstation; (ii) The prototype only simulates a multi-node setting; (iii) Prototype integration into resource-constrained applications is challenging. To bridge the gap between theory and practice, we present a self-contained implementation of FedNL, FedNL-LS, and FedNL-PP for single-node and multi-node settings. Our work resolves the aforementioned issues and reduces the wall clock time by x1000. With this FedNL outperforms alternatives for training logistic regression in a single-node - CVXPY ([arXiv:1603.00943](https://arxiv.org/abs/1603.00943)), and in a multi-node - Apache Spark ([arXiv:1505.06807](https://arxiv.org/abs/1505.06807)), Ray/Scikit-Learn ([arXiv:1712.05889](http://arxiv.org/abs/1712.05889)). Finally, we propose two practical-orientated compressors for FedNL - adaptive TopLEK and cache-aware RandSeqK, which fulfill the theory of FedNL.

## uFedNL Links

- **The arXiv preprint**: [https://arxiv.org/abs/2410.08760](https://arxiv.org/abs/2410.08760)
- **The arXiv preprint in KAUST Library repository**: [https://repository.kaust.edu.sa/items/2ac30675-eb6f-4980-a489-70abe79e888e](https://repository.kaust.edu.sa/items/2ac30675-eb6f-4980-a489-70abe79e888e)
- **The GitHub repository**: [https://github.com/burlachenkok/ufednl](https://github.com/burlachenkok/ufednl)
- **Relative posts**: [https://burlachenkok.github.io/ufednl-in-arxiv/](https://burlachenkok.github.io/ufednl-in-arxiv/)

---

# Federated Learning is Better with Non-Homomorphic Encryption

## PermK/AES Abstract

Traditional AI methodologies necessitate centralized data collection, which becomes impractical when facing problems with network communication, data privacy, or storage capacity. 
Federated Learning (<span style="color:rgb(122,76,24)">FL</span>) offers a paradigm that empowers distributed AI model training without collecting raw data. There are different choices for providing privacy during <span style="color:rgb(122,76,24)">FL</span> training. One of the popular methodologies is employing Homomorphic Encryption (<span style="color:rgb(122,76,24)">HE</span>) - a breakthrough in privacy-preserving computation from Cryptography. However, these methods have a serious price in the form of extra computation and memory footprint.
To resolve these issues, we propose an innovative framework that synergizes permutation-based compressors with Classical Cryptography, even though employing Classical Cryptography was assumed to be impossible in the past in the context of <span style="color:rgb(122,76,24)">FL</span>.
Our framework offers a way to replace <span style="color:rgb(122,76,24)">HE</span> with cheaper Classical Cryptography primitives to provide security for the training process. It fosters asynchronous communication and provides flexible deployment options in various communication topologies. Our work opens a new possibility for applying Classical Cryptography to <span style="color:rgb(122,76,24)">FL</span> and challenges existing claims about its limitations which has been done in previous works.


## PermK/AES Links

- **The arXiv preprint**: [https://arxiv.org/abs/2312.02074](https://arxiv.org/abs/2312.02074)
- **The arXiv preprint in KAUST Library repository**: [https://repository.kaust.edu.sa/items/e36d4766-a879-4ea4-94eb-6c969eadbebc](https://repository.kaust.edu.sa/items/e36d4766-a879-4ea4-94eb-6c969eadbebc)
- **The GitHub repository**: [https://github.com/burlachenkok/fl-with-nonhe](https://github.com/burlachenkok/fl-with-nonhe)
- **Relative posts**: [https://burlachenkok.github.io/add-insights-in-dcgd-permk-aes/](https://burlachenkok.github.io/add-insights-in-dcgd-permk-aes/), [https://burlachenkok.github.io/FL-Privacy-From-Compressor-Accepted-on-DML2023/](https://burlachenkok.github.io/FL-Privacy-From-Compressor-Accepted-on-DML2023/)

---

<center>
<table style="text-align:center;">
<tr>
<td style="padding:30px;text-align:center;vertical-align:middle;"> <img height="115px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td>
</tr>
</table>
</center>
