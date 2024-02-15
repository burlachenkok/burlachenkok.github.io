---
layout: post
title: Unlocking FedNL at Rising Stars AI Symposium 2024.
published: true
---

**"Unlocking FedNL: Self-Contained Compute-Optimized Implementation"** will be presented at [KAUST Rising Stars AI Symposium 2024](https://cemse.kaust.edu.sa/ai/aii-symp-2024).

---

I am glad to have the opportunity to present our recent work *Unlocking FedNL: Self-Contained Compute-Optimized Implementation* at [Rising Stars AI Symposium 2024](https://cemse.kaust.edu.sa/ai/aii-symp-2024).

**Abstract.** Federated Learning (FL) is an emerging paradigm that enables a possibly huge number of intelligent agents to collaboratively train 
Machine Learning (ML) models in a distributed manner, eliminating the need for sharing their local data. 
The recent work ([Safaryan et al., 2021](https://icml.cc/virtual/2022/spotlight/17084)) introduces a family of Federated Newton Learn ([FedNL](https://arxiv.org/abs/2106.02969)) algorithms, 
marking a significant step towards applying second-order methods to FL and large-scale optimization. However, the reference [FedNL](https://arxiv.org/abs/2106.02969) prototype exhibits three practical drawbacks: 

1. It requires $$4.8$$ hours to launch a single experiment in a server-grade workstation.
2. The prototype supports only a single node.
3. The <span style="color:rgb(108,57,0)">FedNL</span> algorithms family prototypes were created in the scripting language [Python](https://www.python.org/). Integration of such implementation into resource-constrained ML applications is challenging.

To bridge the gap between theory and practice, we present a self-contained implementation of <span style="color:rgb(108,57,0)">FedNL</span>, <span style="color:rgb(108,57,0)">FedNL-LS</span>, <span style="color:rgb(108,57,0)">FedNL-PP</span> for single-node and multi-node scenarios. Our work resolves the aforementioned issues in the following sense:

**A)** The work reduces the wall clock time by $$\times 1000$$ in single-node simulation. 

**B)** We do not depend on any 3rd party computation and data processing software frameworks. We tested our implementation on [[x86-64](https://en.wikipedia.org/wiki/X86-64), [AArch64](https://en.wikipedia.org/wiki/AArch64)] x [ [macOS](https://en.wikipedia.org/wiki/MacOS), [Linux](https://en.wikipedia.org/wiki/Linux), [Windows](https://en.wikipedia.org/wiki/Microsoft_Windows) ]. In principle, it can be run on any [POSIX](https://en.wikipedia.org/wiki/POSIX) and [WinAPI](https://en.wikipedia.org/wiki/Windows_API) compatible Operating Systems with available [ISO/IEC 14882 C++2020](https://www.iso.org/standard/79358.html) compiler. 
For multi-node settings, we do not require the ability to have the opportunity to build or use any specific middleware communication library in your OS. But your hardware and OS software stack should support either [TCP/IPv4](https://en.wikipedia.org/wiki/Internet_protocol_suite) or [TCP/IPv6](https://en.wikipedia.org/wiki/Internet_protocol_suite) via standard [Berkley Sockets API](https://en.wikipedia.org/wiki/Berkeley_sockets).

**C)** As a part of the project we proposed two practical-orientated compressors for <span style="color:rgb(108,57,0)">FedNL</span>:

* Adaptive contractive compressor <span style="color:rgb(108,57,0)">TopLEK</span> build on top of <span style="color:rgb(108,57,0)">TopK</span> compressor.
* Cache-aware <span style="color:rgb(108,57,0)">RandSeqK</span> build on top of <span style="color:rgb(108,57,0)">RandK</span> randomized sparsification compressor.

**D)** Finally <span style="color:rgb(108,57,0)">FedNL</span> outperforms alternatives employed for training logistic regression:
* In a single-node setting - [CVXPY](https://www.cvxpy.org/) ([Diamond & Boyd, 2016](https://arxiv.org/abs/1603.00943)), 
* In a multi-node setting - [Apache Spark](https://spark.apache.org/) ([Meng et al., 2016](https://www.jmlr.org/papers/volume17/15-237/15-237.pdf)), [Rays/Scikit-Learn](https://www.ray.io/) ([Moritz et al., 2018](https://www.usenix.org/system/files/osdi18-moritz.pdf)).


---

**Scope of our Work.** We believe our work will be of interest to the audience working in ML in general (and in FL in particular) because half of the established principles are general enough and valuable in scenarios when a theoretically compelling ML algorithm requires a strong implementation. I am glad that (almost all) the previous work authors on top of which we built this practical implementation plan participated in [KAUST Rising Stars in AI Symposium 2024](https://cemse.kaust.edu.sa/ai/aii-symp-2024):

* [M.Safaryan](https://scholar.google.com/citations?user=dJNwgT8AAAAJ&hl=en). Postdoctoral MSCA Fellow, [IST Austria](https://ist.ac.at/en/home/).
* [R.Islamov](https://rustem-islamov.github.io/). PhD student, [University of Basel](https://www.unibas.ch/en.html).
* Prof. [P.Richtárik](https://richtarik.org/). Professor of Computer Science, [KAUST](https://kaust.edu.sa/en).

---

**About Event.**

* [Rising Stars in AI Symposium 2024](https://cemse.kaust.edu.sa/ai/aii-symp-2024):
* [Registration Link](https://docs.google.com/forms/d/e/1FAIpQLSfcxV5n66ou2DnYXe6qm3hmKbUJkmItKpMqSwdrzBkYKIl2Ag/viewform)
* **Date and Time:** February 19 - February 21, UTC+3.
* **Location:** Building 19, Halls 1,2,3, 4700 King Abdullah University of Science and Technology, Thuwal 23955-6900, Saudi Arabia.

---

<table style="text-align:center;">
<tr>
<table>
<tr>
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/kaust_ai_symposium_2024.png"/> </td> 
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.svg"/> </td>
</tr>
</table>
