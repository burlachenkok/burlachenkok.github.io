---
layout: post
title: Extra Comments on the paper Federated Learning is Better with Non-Homomorphic Encryption
published: true
---

Extra Comments on the paper Federated Learning is Better with Non-Homomorphic Encryption *Published on 05 December 2023*

---

Homomorphic encryption has been a highly discussed topic in recent research, particularly regarding its potential use in privacy-preserving Federated Learning (FL). In collaboration with my great peers, [Abdulmajeed Alrowith](https://www.linkedin.com/in/aalrowithi?originalSubdomain=sa), [Fahad Ali Albalawi](https://www.linkedin.com/in/fahad-albalawi-49b55759/), and Prof. [Peter Richtárik](https://richtarik.org/) we explored an intriguing connection between **discrete math cryptographic primitives** and **continuous optimization**.

Our work, titled **"Federated Learning is Better with Non-Homomorphic Encryption,"** was accepted as part of the technical program for the [4th International Workshop on Distributed Machine Learning (DistributedML 2023)](https://distributedml.org/), which was co-located with [CoNext](https://co-next.org/) on **8th December 2023**. 

In the present post, I'd like to share some additional comments on our work, which I hope will inspire further research on the subject of non-homomorphic encryption in Federated Learning.

---

# Abstract

Traditional AI methodologies often rely on centralized data collection, which can be impractical due to issues with network communication, data privacy, or storage capacity. **Federated Learning (FL)** offers an alternative by enabling distributed AI model training without the need for raw data to be collected centrally. There are several ways to ensure privacy during FL training, with **Homomorphic Encryption (HE)** being one of the most well-known. While HE is a breakthrough in privacy-preserving computation, it comes with a significant cost in terms of computation and memory overhead. Our innovative framework combines **permutation-based compressors** with **Classical Cryptography**, addressing the limitations of HE in FL. This approach replaces HE with more efficient Classical Cryptography primitives, reducing computational and memory requirements while still providing security for the training process. The framework also enables asynchronous communication and supports flexible deployment in various network topologies.

Traditional AI methodologies necessitate centralized data collection, which becomes impractical when problems with network communication, data privacy, or storage capacity arise. 
Federated Learning (<span style="color:rgb(122,76,24)">FL</span>) offers a paradigm that empowers distributed AI model training without collecting raw data. There are different choices for providing privacy during <span style="color:rgb(122,76,24)">FL</span> training. One of the popular methodologies is employing Homomorphic Encryption (<span style="color:rgb(122,76,24)">HE</span>) - a breakthrough in privacy-preserving computation from Cryptography. However, these methods have a serious price in the form of extra computation and memory footprint.
To resolve these issues, we propose an innovative framework that synergizes permutation-based compressors with Classical Cryptography, even though employing Classical Cryptography was assumed to be impossible in the past in the context of <span style="color:rgb(122,76,24)">FL</span>.
Our framework offers a way to replace <span style="color:rgb(122,76,24)">HE</span> with cheaper Classical Cryptography primitives to provide security for the training process. It fosters asynchronous communication and provides flexible deployment options in various communication topologies.


---

# Extra Comments

Additional comments are presented below.


## Comment A: Challenging the Status Quo on the un-applicability of classical Ciphers for FL

Our work opens up new possibilities for applying **Classical Cryptography** to **Federated Learning (FL)** and challenges existing claims about its limitations. 

These claims have been stated by various scientists and researchers, including:

* **[ G.Kaissis, M. Makowski, D.Rückert, R.Braren: Secure, privacy-preserving, and federated machine learning in medical imaging, Nature Machine Intelligence, 2020.](https://www.nature.com/articles/s42256-020-0186-1)**
    > "Since only certain mathematical operations, such as addition and multiplication, are homomorphic, the application of HE to neural networks requires the operations defined within the algorithm to conform to these limitations and thus standard encryption algorithms like the advanced encryption standard (AES) cannot be used..."

* **[Kristin E. Lauter: Private Artificial Intelligence: Machine Learning on Encrypted Data, SIAM, 2022.](https://www.siam.org/publications/siam-news/articles/private-artificial-intelligence-machine-learning-on-encrypted-data)**
    > "One way to protect privacy is to lock down sensitive information by encrypting data before it is used for training or prediction. However, traditional encryption schemes do not allow for any computation on encrypted data. We therefore need a new kind of encryption that maintains the data’s structure so that meaningful computation is possible..."

* **[ Pan Y. et al: FedSHE privacy-preserving and efficient federated learning with adaptive segmented CKKS homomorphic encryption, Cybersecurity, 2024.](https://cybersecurity.springeropen.com/articles/10.1186/s42400-024-00232-w)**
    > "Traditional encryption schemes such as AES and DES necessitate decryption of ciphertext before performing computations, rendering them unsuitable for FL..."

* **[N. Jain, A. Cherukuri: Revisiting Fully Homomorphic Encryption Schemes, 2023.](https://arxiv.org/abs/2305.05904)**
    > "Encryption methods like RSA, AES, and DES are not homomorphic, meaning that they require the data to be decrypted before any computation can be performed. This makes it challenging to use these encryption methods in situations where data privacy is a critical concern, such as cloud computing and data analytics..."


---

## Comment B: Links to our paper and recorded video with presentation:

* [Official Publication - ACM Digital Library](https://dl.acm.org/doi/10.1145/3630048.3630182)
* [Presentation Video on YouTube](https://www.youtube.com/watch?v=c0xkiP3cRyY)
* [Extended Version on arXiv](https://arxiv.org/abs/2312.02074)

---

## Comment C: About Appendix

Our paper includes an Appendix with additional details about our framework:

* The impact of the optimization problem's dimension
* Overlapping communication and computation during model training
* Deployment options of our framework in various network topologies
* Connections and influence of the work to other aspects of end-to-end DL training
