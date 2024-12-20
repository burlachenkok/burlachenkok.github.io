---
layout: post
title: Extra Comments on the Paper Federated Learning is Better with Non-Homomorphic Encryption
published: true
---

Extra Comments on the paper Federated Learning is Better with Non-Homomorphic Encryption *Published on 05 December 2023*

---

Homomorphic Encryption has been a highly discussed topic in recent research, particularly regarding its potential use in privacy-preserving Federated Learning (FL). With my peers, [Abdulmajeed Alrowith](https://www.linkedin.com/in/aalrowithi?originalSubdomain=sa), [Fahad Ali Albalawi](https://www.linkedin.com/in/fahad-albalawi-49b55759/), Saudi Data and AI Authority and Prof. [Peter Richtárik](https://richtarik.org/) from King Abdullah University of Science and Technology (ranked #1 in the Arabic World in [2023](https://www.kaust.edu.sa/en/news/kaust-ranked-1-in-times-higher-education-arab-university-rankings-2023), [2024](https://www.kaust.edu.sa/en/news/a-national-pride-kaust-tops-the-arab-university-rankings-for-second-year-in-a-row)) we have discovered an intriguing way connect **discrete math cryptographic primitives** and **continuous optimization primitives**.

The result of our discovery is the work, titled **"Federated Learning is Better with Non-Homomorphic Encryption,"** which was accepted as part of the technical program for the [4th International Workshop on Distributed Machine Learning (DistributedML 2023)](https://distributedml.org/), co-located with [ACM CoNext](https://co-next.org/) on **8th December 2023**.

With the same security level our work practically outperforms Cheon-Kim-Kim-Song(CKKS schema) in terms of communicated information from client to master and from master to client by factor **x500**.

* [https://dl.acm.org/doi/10.1145/3630048.3630182](https://dl.acm.org/doi/10.1145/3630048.3630182) - the official publication.

* [https://arxiv.org/abs/2312.02074](https://arxiv.org/abs/2312.02074) - a bit extended version of the official publication available in arXiv.

* [https://www.youtube.com/watch?v=c0xkiP3cRyY](https://www.youtube.com/watch?v=c0xkiP3cRyY) - the recorded video of the presentation.


In the present post, I'd like to share some additional comments on our work, which I hope will inspire further research on top of our work.

---

# Challenging the Status Quo on the un-applicability of Classical Ciphers for FL

Our work opens up new possibilities for applying **Classical Cryptography** to **Federated Learning (FL)** and challenges existing claims about its limitations made by various scientists:

* **[ G.Kaissis, M. Makowski, D.Rückert, R.Braren: Secure, privacy-preserving, and federated machine learning in medical imaging, Nature Machine Intelligence, 2020.](https://www.nature.com/articles/s42256-020-0186-1)**
    > "Since only certain mathematical operations, such as addition and multiplication, are homomorphic, the application of HE to neural networks requires the operations defined within the algorithm to conform to these limitations and thus standard encryption algorithms like the advanced encryption standard (AES) cannot be used..."

* **[Kristin E. Lauter: Private Artificial Intelligence: Machine Learning on Encrypted Data, SIAM, 2022.](https://www.siam.org/publications/siam-news/articles/private-artificial-intelligence-machine-learning-on-encrypted-data)**
    > "One way to protect privacy is to lock down sensitive information by encrypting data before it is used for training or prediction. However, traditional encryption schemes do not allow for any computation on encrypted data. We therefore need a new kind of encryption that maintains the data’s structure so that meaningful computation is possible..."

* **[ Pan Y. et al: FedSHE privacy-preserving and efficient federated learning with adaptive segmented CKKS homomorphic encryption, Cybersecurity, 2024.](https://cybersecurity.springeropen.com/articles/10.1186/s42400-024-00232-w)**
    > "Traditional encryption schemes such as AES and DES necessitate decryption of ciphertext before performing computations, rendering them unsuitable for FL..."

* **[N. Jain, A. Cherukuri: Revisiting Fully Homomorphic Encryption Schemes, 2023.](https://arxiv.org/abs/2305.05904)**
    > "Encryption methods like RSA, AES, and DES are not homomorphic, meaning that they require the data to be decrypted before any computation can be performed. This makes it challenging to use these encryption methods in situations where data privacy is a critical concern, such as cloud computing and data analytics..."

---

# Comments About Appendix of the Paper

Our paper includes an Appendix providing additional details about our framework, including:

* The effect of the optimization problem's dimensionality.
* Techniques for overlapping communication and computation during model training.
* Deployment strategies for our framework across various network topologies.
* The framework's connections to and influence on other aspects of end-to-end deep learning training.

