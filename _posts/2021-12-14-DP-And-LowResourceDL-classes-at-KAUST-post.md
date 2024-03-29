---
layout: post
title: Fall 2021 Differential Privacy and Efficient DL classes at KAUST as CEMSE/CS Ph.D.
published: true
---

"Differential Privacy" and "Efficient Deep Learning" classes at KAUST.

---

# Classes that I took (CS326, CS394S):

As a subpart of my academic load in Fall 2021, I took two classes CS326 Low Resource DL and CS394S Contemporary Topics in Computer Security.

In this post, I would like to give some small insides about all of them.

## [CS394S Contemporary Topics in Computer Secutiry](https://registrar-programguide.kaust.edu.sa/Courses/CS-Computer-Science/300/CS-394)

At first glance, it may seem that anonymizing a dataset via stripping it of identifying information about individuals, such as names, addresses, etc., is sufficient to preserve
the privacy of the data. However, **this is problematic** because an adversary may have some auxiliary information, which may even be publicly available, and can be used to
attack mathematical models that take private data as input. Differential Privacy(DP) has become the de facto standard for guaranteeing machine learning and statistical analysis privacy. 

A Differentially Private (DP) algorithm guarantees that a single user's input won't significantly change the output distribution of the algorithm. 
A Differential Privacy is an approach to the randomized algorithm that uses data as input. 

The CS394S covered a lot of aspects of DP and contained 20 lectures, four assignments with theory and practice, four quizzes, final project.
There are a lot of materials that have been covered during 20 lectures. This is a very good course that covers various aspects of Differential Privacy and topics inludes:
* Reconstruction Attacks, Definitions and Key properties of Pure and Approximate Differential Privacy, Exponential Mechanism, Noisy Max Mechanism, Gaussian, and Laplace Mechanisms,
* Subsampling Properties, Renyi Differential Privacy, Sparse Vector Technique, Local Sensitive Methods and its problems, Propose-Test-Release Mechanism, Smooth Sensitivity
* Differentially Private Empirical Risk Minimization
* Local Differential Privacy methods without a trusted curator
* Releasing Multiple Linear Queries Privately and Suffled DP


The course was taught by [prof. Di Wang](https://www.kaust.edu.sa/en/study/faculty/di-wang) and during lectures, the different styles have been used - sometimes it was sliding, sometimes lecture notes, sometimes whiteboard.
The DP is important for my area of research (Federated Learning), but in general, I think it may be interesting for people in STATS as well.
DP really exploits heavily various statistical theorems and bounds to construct worst-case probabilistic garantees relative to data privacy.

In my project, I have made reviewed several papers viewing from the point of view of the connection of DP with Math Optimization in the context of solving ERM formulation.

## [CS326 Efficient Deep Learning](https://registrar-programguide.kaust.edu.sa/en/Courses/CS-Computer-Science/300/CS-326)

Before going into that class, it's better to know in advance what classical Deep Learning models, CNNs, and LSTMS are and what practices are used to work with them.

The course provides the ability to build more efficient systems for some important machine learning problems, and topics include:

* Few-shot learning, zero-shot learning, long-tail recognition
* Compositional machine learning, causal deep learning, self-supervised learning
* Meta-Learning, Multi-Task Learning
* GANs and Generative Zero-Shot Learning
* Efficient training for Transformers and Graph Convolution Networks

In terms of the academic load, it includes three assignments, but most grade depends on a course project. If you are targeting grade A, it's better to start work on the project as soon as possible.

The course is very interesting and covers several recent DL relative activities in the area of Machine Learning.

Also [prof. Mohamed Elhoseiny](https://www.kaust.edu.sa/en/study/faculty/mohamed-elhoseiny) is a very interactive professor.
