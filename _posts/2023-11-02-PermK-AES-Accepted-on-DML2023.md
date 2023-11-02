---
layout: post
title: Federated Learning is Better with Non-Homomorphic Encryption at DistributedML 2023
published: true
---

The paper "Federated Learning is Better with Non-Homomorphic Encryption" was accepted by the [DistributedML 2023](https://distributedml.org/).

---

The paper, titled *"Federated Learning is Better with Non-Homomorphic Encryption"*, has been accepted as part of the technical program for the [19th ACM International Conference on Emerging Networking EXperiments and Technologies (ACM CoNEXT 2023)](https://conferences2.sigcomm.org/co-next/2023/), Paris, an education conference sponsored by the [Association for Computing Machinery (ACM)](https://www.acm.org/).
The [Association for Computing Machinery (ACM)](https://www.acm.org/) is the world’s leading educational and scientific computing society and the resource for lifelong learning in the rapidly changing field.

I was glad to work with my peers and hope for further cooperation with them:
* [Abdulmajeed Alrowith](https://www.linkedin.com/in/aalrowithi?originalSubdomain=sa) from [Saudi Data and AI Authority](https://sdaia.gov.sa/).
* [Fahad Ali Albalawi](https://www.linkedin.com/in/fahad-albalawi-49b55759/) from [Saudi Data and AI Authority](https://sdaia.gov.sa/) during working under the project.
* My advisor Prof. [Peter Richtarik](https://richtarik.org/) from [King Abdullah University of Science and Technology](https://www.kaust.edu.sa/)

Traditional AI methodologies necessitate centralized data collection, which becomes impractical when facing problems with network communication, data privacy, or storage capacity. 
Federated Learning (FL) offers a paradigm that empowers distributed AI model training without collecting raw data. 

There are different choices for providing privacy during FL training. One of the popular methodologies is employing Homomorphic Encryption (HE) - a breakthrough in privacy-preserving computation from Cryptography. However, these methods have a price in the form of extra computation and memory footprint.
To resolve these issues, we propose an innovative framework that synergizes permutation-based compressors with Classical Cryptography, even though employing Classical Cryptography was assumed to be impossible in the past in the context of FL.
Our framework offers a way to replace HE with cheaper Classical Cryptography primitives to provide security for the training process. It fosters asynchronous communication and provides flexible deployment options in various communication topologies.

Our work opens a new possibility for applying Classical Cryptography to FL and challenges some existing claims about its limitations which has been done in works such as:
* [G.Kaissis, M.Makowski, D.Rückert, R.Braren, 2020. Secure, privacy-preserving, and federated machine learning in medical imaging. Nature Machine Intelligence 2, 6 (2020)](https://www.nature.com/articles/s42256-020-0186-1)
* [N.Jain, A.Cherukuri, 2023. Revisiting Fully Homomorphic Encryption Schemes.](https://arxiv.org/abs/2305.05904)

Our paper will be presented in [4th International Workshop on Distributed Machine Learning (DistributedML 2023) co-located with CoNext](https://distributedml.org/) and will be available in [ACM Digital Library. Conext proceedings](https://dl.acm.org/conference/conext/proceedings).
The [ACM CoNEXT 2023](https://conferences2.sigcomm.org/co-next/2023/) will be held December 5-8, 2023 in the Conservatoire national des arts et métiers (Cnam), Paris, France. 
If I will obtain VISA to France I will be glad to have a discussion during or after the the presentation.

---

<table style="text-align:center;">
<tr>
<td> <img height="100px" src="https://burlachenkok.github.io/materials/clean-logo-white-background-small.png"/> </td>
<td> <img height="100px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.png"/> </td> 
<td> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.png"/> </td> 
<td> <img height="100px" src="https://burlachenkok.github.io/materials/acm-logo.png"/> </td>
</tr>
</table>
