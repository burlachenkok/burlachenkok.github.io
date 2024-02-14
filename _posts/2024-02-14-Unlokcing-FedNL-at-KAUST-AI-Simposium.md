---
layout: post
title: Unlocking FedNL: Self-Contained Compute-Optimized Implementation
published: true
---

Unlocking FedNL: Self-Contained Compute-Optimized Implementation at [Rising Stars in AI Symposium 2024](https://cemse.kaust.edu.sa/ai/aii-symp-2024).

---


Federated Learning (FL) is an emerging paradigm that enables a possibly huge number of intelligent agents to collaboratively train 
Machine Learning (ML) models in a distributed manner, eliminating the need for sharing their local data. 
The recent work (Safaryan et al., 2021) introduces a family of Federated Newton Learn (FedNL) algorithms, 
marking a significant step towards applying second-order methods to FL and large-scale optimization. 

However, the reference FedNL prototype exhibits three practical drawbacks: 

* (i) It requires $4.8$ hours to launch a single experiment in a sever-grade workstation
* (ii) The prototype supports only a single node
* (iii) Prototype integration into resource-constrained ML applications is challenging

To bridge the gap between theory and practice, we present a self-contained implementation of FedNL, FedNL-LS, and FedNL-PP for single-node and 
multi-node scenarios. Our work resolves the aforementioned issues and reduces the wall clock time by $\times 1000$. 

With this FedNL outperforms alternatives employed for training logistic regression in a single-node - CVXPY (Diamond & Boyd, 2016), 
and in a multi-node - Apache Spark (Meng et al., 2016), Rays/Scikit-Learn (Moritz et al., 2018). 

Finally, we propose two practical-orientated compressors for FedNL - adaptive TopLEK and cache-aware RandSeqK.


---
We hope our work will be interesting for the auditorium. To the best of our knowledge the authors of previous work on top of which we build this practical implementation a plan to participate in this event:
* [M.Safaryan](https://scholar.google.com/citations?user=dJNwgT8AAAAJ&hl=en)
* [R.Islamov](https://rustem-islamov.github.io/), [X.Qian](https://qianxunk.github.io/)
* [P.Richtárik](https://richtarik.org/) 

*FedNL: Making Newton-Type Methods Applicable to Federated Learning* ([arXiv:2106.02969](https://arxiv.org/abs/2106.02969), 
[ICML 2021](https://icml.cc/virtual/2022/spotlight/17084)) 

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
