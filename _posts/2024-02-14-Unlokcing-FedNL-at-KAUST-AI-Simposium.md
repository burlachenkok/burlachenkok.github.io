---
layout: post
title: Unlocking FedNL: Self-Contained Compute-Optimized Implementation
published: true
---

Unlocking FedNL: Self-Contained Compute-Optimized Implementation at [Rising Stars in AI Symposium 2024](https://cemse.kaust.edu.sa/ai/aii-symp-2024).

---


Federated Learning (FL) is an emerging paradigm that enables a possibly huge number of intelligent agents to collaboratively train 
Machine Learning (ML) models in a distributed manner, eliminating the need for sharing their local data. 
The recent work ([Safaryan et al., 2021](https://icml.cc/virtual/2022/spotlight/17084)) introduces a family of Federated Newton Learn ([FedNL](https://arxiv.org/abs/2106.02969)) algorithms, 
marking a significant step towards applying second-order methods to FL and large-scale optimization. 

However, the reference [FedNL](https://arxiv.org/abs/2106.02969) prototype exhibits three practical drawbacks: 

* (i) It requires $4.8$ hours to launch a single experiment in a sever-grade workstation
* (ii) The prototype supports only a single node
* (iii) Prototype integration into resource-constrained ML applications is challenging

To bridge the gap between theory and practice, we present a self-contained implementation of <span style="color:rgb(108,57,0)">FedNL</span>, <span style="color:rgb(108,57,0)">FedNL-LS</span>, <span style="color:rgb(108,57,0)">FedNL-PP</span> for single-node and multi-node scenarios. 
Our work resolves the aforementioned issues and reduces the wall clock time by $\times 1000$. 

With this FedNL outperforms alternatives employed for training logistic regression in a single-node - [CVXPY](https://www.cvxpy.org/) ([Diamond & Boyd, 2016](https://arxiv.org/abs/1603.00943)), 
and in a multi-node - [Apache Spark](https://spark.apache.org/) ([Meng et al., 2016](https://www.jmlr.org/papers/volume17/15-237/15-237.pdf)), [Rays/Scikit-Learn](https://www.ray.io/) ([Moritz et al., 2018](https://www.usenix.org/system/files/osdi18-moritz.pdf)).

Finally, we propose two practical-orientated compressors for FedNL:
* Adaptive <span style="color:rgb(108,57,0)">TopLEK</span>
* Cache-aware <span style="color:rgb(108,57,0)">RandSeqK</span>


---

We hope our work will be interesting for the general auditorium because half of the established principles are general enough and are valuable in scenarios 
where a theoretically compelling ML algorithm requires a strong implementation.

In fact, to the best of our knowledge the authors of previous work on top of which we build this practical implementation a plan to participate in this event:
* [M.Safaryan](https://scholar.google.com/citations?user=dJNwgT8AAAAJ&hl=en)
* [R.Islamov](https://rustem-islamov.github.io/), [X.Qian](https://qianxunk.github.io/)
* [P.Richtárik](https://richtarik.org/) 


---

* [Link for event](https://cemse.kaust.edu.sa/ai/aii-symp-2024)
* [Link for registration](https://docs.google.com/forms/d/e/1FAIpQLSfcxV5n66ou2DnYXe6qm3hmKbUJkmItKpMqSwdrzBkYKIl2Ag/viewform).
* **Date and Time:** February 19 - February 21, UTC+3.
* **Location:** Building 19, Halls 1,2,3, 4700 King Abdullah University of Science and Technology, Thuwal 23955-6900, Saudi Arabia.


---

<table style="text-align:center;">
<tr>
<td style="text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.svg"/> </td> 
</tr>
</table>

<table style="text-align:center;">
<tr>
<td style="text-align:center;vertical-align:middle;"> <img height="50px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
</tr>
</table>
