---
layout: post
title: Extra Comments on Federated Learning is Better with Non-Homomorphic Encryption
published: false
---

Extra Comments on **"Federated Learning is Better with Non-Homomorphic Encryption"**


---


Homomorphic encryption has been a hot research topic in recent years. However, our style of research bridges the fields. 

In the past I was glad to discover with my peers one connection between **discrete math objects** and **continuous math objects**.

The paper **"Federated Learning is Better with Non-Homomorphic Encryption"** has been accepted as part of the technical program for the 
[4th International Workshop on Distributed Machine Learning (DistributedML 2023) co-located with CoNext](https://distributedml.org/) on the **8th of December 2023** and is available in [ACM CoNEXT Proceedings in ACM Digital Library](https://dl.acm.org/conference/conext/proceedings).

---

Links to our paper and recorded video with presentation:
* [https://dl.acm.org/doi/10.1145/3630048.3630182](https://dl.acm.org/doi/10.1145/3630048.3630182) - the official publication.
* [https://arxiv.org/abs/2312.02074](https://arxiv.org/abs/2312.02074) - a bit extended version of the official publication.
* [https://www.youtube.com/watch?v=c0xkiP3cRyY](https://www.youtube.com/watch?v=c0xkiP3cRyY) - the recorded video of the presentation.

---

I was glad to work with my peers and hope for further cooperation with them [Abdulmajeed Alrowith](https://www.linkedin.com/in/aalrowithi?originalSubdomain=sa), 
[Fahad Ali Albalawi](https://www.linkedin.com/in/fahad-albalawi-49b55759/), Prof. [Peter Richtárik](https://richtarik.org/) from [King Abdullah University of Science and Technology](https://www.kaust.edu.sa/).

Traditional AI methodologies necessitate centralized data collection, which becomes impractical when problems with network communication, data privacy, or storage capacity arise. 
Federated Learning (<span style="color:rgb(122,76,24)">FL</span>) offers a paradigm that empowers distributed AI model training without collecting raw data. 
There are different choices for providing privacy during <span style="color:rgb(122,76,24)">FL</span> training. One of the popular methodologies is employing Homomorphic Encryption (<span style="color:rgb(122,76,24)">HE</span>) - a breakthrough in privacy-preserving computation from Cryptography. However, these methods have a serious price in the form of extra computation and memory footprint.
To resolve these issues, we propose an innovative framework that synergizes permutation-based compressors with Classical Cryptography, even though employing Classical Cryptography was assumed to be impossible in the past in the context of <span style="color:rgb(122,76,24)">FL</span>.
Our framework offers a way to replace <span style="color:rgb(122,76,24)">HE</span> with cheaper Classical Cryptography primitives to provide security for the training process. It fosters asynchronous communication and provides flexible deployment options in various communication topologies.

We provide an Appendix for our work that includes additional details about our framework:
* Studies about the effect of the optimization problem dimension
* Overlapping communication and computation during training machine learning models
* Deployment options of our framework in various network topologies

---

What is important our work opens a new possibility for applying Classical Cryptography to <span style="color:rgb(122,76,24)">FL</span> and challenges existing claims about its limitations 
which have been stated by serious scientists in various venues:

* At Nature by [G.Kaissis, M. Makowski, D.Rückert, R.Braren: Secure, privacy-preserving, and federated machine learning in medical imaging. Nature Machine Intelligence, 2020.](https://www.nature.com/articles/s42256-020-0186-1)

> *..Since only certain mathematical operations, such as addition and multiplication, are homomorphic, the application of HE to neural networks
requires the operations defined within the algorithm to conform to these limitations and thus standard encryption algorithms like the advanced encryption standard (AES) cannot be used...*


* At SIAM by [Kristin E. Lauter: Private Artificial Intelligence: Machine Learning on Encrypted Data, 2022.](https://www.siam.org/publications/siam-news/articles/private-artificial-intelligence-machine-learning-on-encrypted-data) stated that

> *..One way to protect privacy is to lock down sensitive information by encrypting data before it is used for training or prediction. 
However, traditional encryption schemes do not allow for any computation on encrypted data. We therefore need a new kind of encryption that maintains the data’s structure so that meaningful computation is possible...*

* At Cybersecurity by [Pan Y. et al: FedSHE privacy-preserving and efficient federated learning with adaptive segmented CKKS homomorphic encryption, 2024] 

> *...Traditional encryption schemes such as AES and DES necessitate decryption of ciphertext before performing computations, rendering them unsuitable for FL...*


* arXiv preprint from School of Information Technology and Engineering (SITE) Vellore Institute of Technology [N.Jain, A.Cherukuri: Revisiting Fully Homomorphic Encryption Schemes, 2023.](https://arxiv.org/abs/2305.05904)

> *..Encryption methods like RSA, AES, and DES are not homomorphic, meaning that they require the data to be decrypted before any computation can be performed. 
This makes it challenging to use these encryption methods in situations where data privacy is a critical concern, such as cloud computing and data analytics...*
