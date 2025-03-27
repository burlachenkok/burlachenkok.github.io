---
layout: post
title: On making several projects opensource - BurTorch, uFedNL, and PermK/AES
published: true
---

On making several projects opensource - BurTorch, uFedNL, and PermK/AES.

---

I am excited to announce that several of my projects are now open-sourced. 

We have decided to share these projects with the community, hoping to drive collaboration, foster innovation. Below, there is a brief overview of each project.


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
- **Podcast** generated via [NotebookLM](https://notebooklm.google/) in an entertaining format:
    - (i) online: [https://www.podbean.com/eas/pb-en4mf-184b9bf](https://www.podbean.com/eas/pb-en4mf-184b9bf)
    - (ii) offline: [https://burlachenkok.github.io/podcasts/burtorch-generated-interview.mp3](https://burlachenkok.github.io/podcasts/burtorch-generated-interview.mp3)
- **The arXiv preprint in KAUST Library repository**: [https://repository.kaust.edu.sa/bitstreams/0997f91f-441a-4f16-9003-3e33e729134e/download](https://repository.kaust.edu.sa/bitstreams/0997f91f-441a-4f16-9003-3e33e729134e/download)
- **The GitHub repository**: [https://github.com/burlachenkok/burtorch](https://github.com/burlachenkok/burtorch)

---

# Unlocking FedNL: Self-Contained Compute-Optimized Implementation


## Unlocking FedNL Links Abstract

Federated Learning (FL) is an emerging paradigm that enables intelligent agents to collaboratively train Machine Learning (ML) models in a distributed manner, eliminating the need for sharing their local data. The recent work ([arXiv:2106.02969](https://arxiv.org/abs/2106.02969)) introduces a family of Federated Newton Learn (FedNL) algorithms, marking a significant step towards applying second-order methods to FL and large-scale optimization. However, the reference FedNL prototype exhibits three serious practical drawbacks: (i) It requires 4.8 hours to launch a single experiment in a sever-grade workstation; (ii) The prototype only simulates multi-node setting; (iii) Prototype integration into resource-constrained applications is challenging. To bridge the gap between theory and practice, we present a self-contained implementation of FedNL, FedNL-LS, and FedNL-PP for single-node and multi-node settings. Our work resolves the aforementioned issues and reduces the wall clock time by x1000. With this FedNL outperforms alternatives for training logistic regression in a single-node - CVXPY ([arXiv:1603.00943](https://arxiv.org/abs/1603.00943)), and in a multi-node - Apache Spark ([arXiv:1505.06807](https://arxiv.org/abs/1505.06807)), Ray/Scikit-Learn ([arXiv:1712.05889](http://arxiv.org/abs/1712.05889)). Finally, we propose two practical-orientated compressors for FedNL - adaptive TopLEK and cache-aware RandSeqK, which fulfill the theory of FedNL.

## Unlocking FedNL Links

- **The arXiv preprint**: [https://arxiv.org/abs/2410.08760](https://arxiv.org/abs/2410.08760)
- **Podcast** generated via [NotebookLM](https://notebooklm.google/) in an entertaining format: 
     - (i) online [https://www.podbean.com/eas/pb-zs34b-16d2942](https://www.podbean.com/eas/pb-zs34b-16d2942) 
     - (ii) offline [(https://burlachenkok.github.io/podcasts/u-fednl-before-rebuttal.mp3](https://burlachenkok.github.io/podcasts/u-fednl-before-rebuttal.mp3).
- **The arXiv preprint in KAUST Library repository**: [https://repository.kaust.edu.sa/items/2ac30675-eb6f-4980-a489-70abe79e888e](https://repository.kaust.edu.sa/items/2ac30675-eb6f-4980-a489-70abe79e888e)
- **The GitHub repository**: [https://github.com/burlachenkok/ufednl](https://github.com/burlachenkok/ufednl)


---

# Federated Learning is Better with Non-Homomorphic Encryption

## Abstract

Traditional AI methodologies necessitate centralized data collection, which becomes impractical when facing problems with network communication, data privacy, or storage capacity. 
Federated Learning (<span style="color:rgb(122,76,24)">FL</span>) offers a paradigm that empowers distributed AI model training without collecting raw data. There are different choices for providing privacy during <span style="color:rgb(122,76,24)">FL</span> training. One of the popular methodologies is employing Homomorphic Encryption (<span style="color:rgb(122,76,24)">HE</span>) - a breakthrough in privacy-preserving computation from Cryptography. However, these methods have a serious price in the form of extra computation and memory footprint.
To resolve these issues, we propose an innovative framework that synergizes permutation-based compressors with Classical Cryptography, even though employing Classical Cryptography was assumed to be impossible in the past in the context of <span style="color:rgb(122,76,24)">FL</span>.
Our framework offers a way to replace <span style="color:rgb(122,76,24)">HE</span> with cheaper Classical Cryptography primitives to provide security for the training process. It fosters asynchronous communication and provides flexible deployment options in various communication topologies.

Our work opens a new possibility for applying Classical Cryptography to <span style="color:rgb(122,76,24)">FL</span> and challenges existing claims about its limitations which has been done in works such as:

* **[ G.Kaissis, M. Makowski, D.Rückert, R.Braren: Secure, privacy-preserving, and federated machine learning in medical imaging, Nature Machine Intelligence, 2020.](https://www.nature.com/articles/s42256-020-0186-1)**
    > "Since only certain mathematical operations, such as addition and multiplication, are homomorphic, the application of HE to neural networks requires the operations defined within the algorithm to conform to these limitations and thus standard encryption algorithms like the advanced encryption standard (AES) cannot be used..."

* **[Kristin E. Lauter: Private Artificial Intelligence: Machine Learning on Encrypted Data, SIAM, 2022.](https://www.siam.org/publications/siam-news/articles/private-artificial-intelligence-machine-learning-on-encrypted-data)**
    > "One way to protect privacy is to lock down sensitive information by encrypting data before it is used for training or prediction. However, traditional encryption schemes do not allow for any computation on encrypted data. We therefore need a new kind of encryption that maintains the data's structure so that meaningful computation is possible..."


* **[N. Jain, A. Cherukuri: Revisiting Fully Homomorphic Encryption Schemes, 2023.](https://arxiv.org/abs/2305.05904)**
    > "Encryption methods like RSA, AES, and DES are not homomorphic, meaning that they require the data to be decrypted before any computation can be performed. This makes it challenging to use these encryption methods in situations where data privacy is a critical concern, such as cloud computing and data analytics..."

* **[ Pan Y. et al: FedSHE privacy-preserving and efficient federated learning with adaptive segmented CKKS homomorphic encryption, Cybersecurity, 2024.](https://cybersecurity.springeropen.com/articles/10.1186/s42400-024-00232-w)**
    > "Traditional encryption schemes such as AES and DES necessitate decryption of ciphertext before performing computations, rendering them unsuitable for FL..."


## DCGD/PermK/AES Links

- **The arXiv preprint**: [https://arxiv.org/abs/2312.02074](https://arxiv.org/abs/2312.02074)
- **The arXiv preprint in KAUST Library repository**: [https://repository.kaust.edu.sa/items/e36d4766-a879-4ea4-94eb-6c969eadbebc](https://repository.kaust.edu.sa/items/e36d4766-a879-4ea4-94eb-6c969eadbebc)
- **The GitHub repository**: [https://github.com/burlachenkok/fl-with-nonhe](https://github.com/burlachenkok/fl-with-nonhe)

---

<center>
<table style="text-align:center;">
<tr>
<td style="padding:30px;text-align:center;vertical-align:middle;"> <img height="115px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td>
</tr>
</table>
</center>
