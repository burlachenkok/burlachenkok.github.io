---
layout: post
title: FL_PyTorch at SIAM Conference on Optimization (OP23)
published: true
---

**"FL_PyTorch: Optimization Research Simulator for Federated Learning"** in [SIAM Conference on Optimization 2023](https://www.siam.org/conferences/cm/conference/op23).

---

# FL_PyTorch at SIAM OP32

I'm excited to speak at the [SIAM Conference on Optimization (OP23)](https://www.siam.org/conferences/cm/conference/op23) in Seattle, U.S. on Friday, June 2, 2023.

Link to my talk: [https://meetings.siam.org/sess/dsp_talk.cfm?p=128776](https://meetings.siam.org/sess/dsp_talk.cfm?p=128776).

My talk will be about FL_PyTorch, a simulator constructed specifically for federated learning optimization research. According to an external assessment carried out in the paper [FeLebrities: a user-centric assessment of Federated Learning Frameworks](https://www.techrxiv.org/articles/preprint/FeLebrities_a_user-centric_assessment_of_Federated_Learning_frameworks/21263013) our solution lie between:

* [TensorFlow Federated](https://www.tensorflow.org/federated), which is an open-source framework for machine learning and other computations on decentralized data, developed by Google.
* [FLUTE](https://www.microsoft.com/en-us/research/blog/flute-a-scalable-federated-learning-simulation-platform/), a scalable federated learning simulation platform, developed by Microsoft Research. 

The funding for my visit is provided by [my advisor Prof. Peter Richtarik](https://richtarik.org/) and [KAUST University](https://www.kaust.edu.sa/). 

I am looking forward to presenting my work and discussing its future prospects.

Unfortunately, I need a [B1 visa](https://travel.state.gov/content/travel/en/us-visas/tourism-visit/visitor.html) to actually come in the U.S., but I don't have it yet. My application for B1 VISA is under administrative processing for two months.

# About Conference

[The SIAM Conference on Optimization (OP23)](https://www.siam.org/conferences/cm/conference/op23) is a conference of the SIAM Activity Group on Optimization that will feature the latest research in theory, algorithms, software and applications for optimization problems
The conference will bring together mathematicians, operations researchers, computer scientists, engineers, software developers and practitioners. The conference will include:

* Invited presentations,
* Minitutorials
* Student activities, 
* Special events and workshops

# Abstract of Talk

Federated Learning (FL) has emerged as a promising technique for edge devices to collaboratively learn a shared machine learning model while keeping training data locally on the device, thereby removing the need to store and access the full data in the cloud. However, FL is difficult to implement, test and deploy in practice considering heterogeneity in common edge device settings, making it fundamentally hard for researchers to efficiently prototype and test their optimization algorithms. In this work, our aim is to alleviate this problem by introducing FL_PyTorch : a suite of open-source software written in python that builds on top of one the most popular research Deep Learning (DL) framework PyTorch. We built FL_PyTorch as a research simulator for FL to enable fast development, prototyping and experimenting with new and existing FL optimization algorithms. Our system supports abstractions that provide researchers with a sufficient level of flexibility to experiment with existing and novel approaches to advance the state-of-the-art. Furthermore, FL_PyTorch is a simple to use console system, allows to run several clients simultaneously using local CPUs or GPU(s), and even remote compute devices without the need for any distributed implementation provided by the user. FL_PyTorch also offers a Graphical User Interface. For new methods, researchers only provide the centralized implementation of their algorithm.

---

<table>
<tr>
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.png"/> </td> 
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/siam-logo-black.png"/> </td> 
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.png"/> </td> 
</tr>
</table>
