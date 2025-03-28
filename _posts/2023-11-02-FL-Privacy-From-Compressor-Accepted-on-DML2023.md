---
layout: post
title: Federated Learning is Better with Non-Homomorphic Encryption
published: true
---

**"Federated Learning is Better with Non-Homomorphic Encryption"** at the [4th International Workshop on Distributed Machine Learning(DistributedML 2023)](https://distributedml.org/).

---

The paper **"Federated Learning is Better with Non-Homomorphic Encryption"** has been accepted as part of the technical program for the [19th ACM International Conference on Emerging Networking EXperiments and Technologies (ACM CoNEXT 2023)](https://conferences2.sigcomm.org/co-next/2023/), a conference sponsored by:

* [Association for Computing Machinery](https://www.acm.org/)
* [Huawei Technologies Co.](https://huawei.com/)
* [Google Inc.](https://about.google/)
* [Comcast Co.](https://corporate.comcast.com/)
* [Réseaux IP Européens Network Coordination Centre](https://www.ripe.net/)
* [Orange S.A. (France Télécom S.A.)](https://www.orange.com/en)

Our paper will be presented at the [4th International Workshop on Distributed Machine Learning (DistributedML 2023) co-located with CoNext](https://distributedml.org/) on the **8th of December 2023** and will be available in [ACM CoNEXT Proceedings in ACM Digital Library](https://dl.acm.org/conference/conext/proceedings).
The [DistributedML](https://distributedml.org/) will take place at the Conservatoire National des Arts et Métiers ([CNAM](https://www.cnam.eu/)) located at [292 Rue Saint-Martin, 75003, Paris, France](https://maps.app.goo.gl/8x8HoPkcmPvDb9TZA).

Information about other workshops within [ACM CoNext 2023](https://conferences2.sigcomm.org/co-next/2023/) is available from this [link](https://conferences2.sigcomm.org/co-next/2023/#!/workshopatglance).

---

Links to our paper and recorded video with presentation:
* [https://dl.acm.org/doi/10.1145/3630048.3630182](https://dl.acm.org/doi/10.1145/3630048.3630182) - the official publication.
* [https://arxiv.org/abs/2312.02074](https://arxiv.org/abs/2312.02074) - a bit extended version of the official publication.
* [https://www.youtube.com/watch?v=c0xkiP3cRyY](https://www.youtube.com/watch?v=c0xkiP3cRyY) - the recorded video of the presentation.

---

I was glad to work with my peers and hope for further cooperation with them:
* [Abdulmajeed Alrowith](https://www.linkedin.com/in/aalrowithi?originalSubdomain=sa) from [Saudi Data and AI Authority](https://sdaia.gov.sa/)
* [Fahad Ali Albalawi](https://www.linkedin.com/in/fahad-albalawi-49b55759/) from [Saudi Data and AI Authority](https://sdaia.gov.sa/)
* Prof. [Peter Richtárik](https://richtarik.org/) from [King Abdullah University of Science and Technology](https://www.kaust.edu.sa/)

Traditional AI methodologies necessitate centralized data collection, which becomes impractical when facing problems with network communication, data privacy, or storage capacity. 
Federated Learning (<span style="color:rgb(122,76,24)">FL</span>) offers a paradigm that empowers distributed AI model training without collecting raw data. There are different choices for providing privacy during <span style="color:rgb(122,76,24)">FL</span> training. One of the popular methodologies is employing Homomorphic Encryption (<span style="color:rgb(122,76,24)">HE</span>) - a breakthrough in privacy-preserving computation from Cryptography. However, these methods have a serious price in the form of extra computation and memory footprint.
To resolve these issues, we propose an innovative framework that synergizes permutation-based compressors with Classical Cryptography, even though employing Classical Cryptography was assumed to be impossible in the past in the context of <span style="color:rgb(122,76,24)">FL</span>.
Our framework offers a way to replace <span style="color:rgb(122,76,24)">HE</span> with cheaper Classical Cryptography primitives to provide security for the training process. It fosters asynchronous communication and provides flexible deployment options in various communication topologies.

Our work opens a new possibility for applying Classical Cryptography to <span style="color:rgb(122,76,24)">FL</span> and challenges existing claims about its limitations which has been done in works such as:
* [G.Kaissis, M.Makowski, D.Rückert, R.Braren: Secure, privacy-preserving, and federated machine learning in medical imaging. Nature Machine Intelligence, 2020.](https://www.nature.com/articles/s42256-020-0186-1)
* [N.Jain, A.Cherukuri: Revisiting Fully Homomorphic Encryption Schemes, 2023.](https://arxiv.org/abs/2305.05904)

As a part of the proceedings, we provide an Appendix for our work that includes additional details about our framework:
* Studies about the effect of the optimization problem dimension
* Overlapping communication and computation during training machine learning models
* Deployment options of our framework in various network topologies


---


<div>
  <center>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/c0xkiP3cRyY?si=XWrESY25gu6gnQJz" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
  </center>
</div>

---

<table style="text-align:center;">
<tr>
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="80px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.svg"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.svg"/> </td> 
<td style="padding:15px;text-align:center;vertical-align:middle;"> <img height="85px" src="https://burlachenkok.github.io/materials/acm-logo.svg"/> </td>
</tr>
</table>
