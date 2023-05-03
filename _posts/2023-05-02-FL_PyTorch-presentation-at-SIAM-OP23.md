---
layout: post
title: FL_PyTorch at SIAM Conference on Optimization (OP23)
published: true
---

**"FL_PyTorch: Optimization Research Simulator for Federated Learning"** at [SIAM Conference on Optimization 2023](https://www.siam.org/conferences/cm/conference/op23).

---

# FL_PyTorch at SIAM OP32

I'm excited to speak at the [SIAM Conference on Optimization (OP23)](https://www.siam.org/conferences/cm/conference/op23) in Seattle, U.S. on Friday, June 2, 2023. The funding for my visit is provided by my advisor [Prof. Peter Richtarik](https://richtarik.org/) and [KAUST University](https://www.kaust.edu.sa/). I am looking forward to presenting my work and discussing its future prospects.

Unfortunately, to actually come to the U.S. I need a [B1 visa](https://travel.state.gov/content/travel/en/us-visas/tourism-visit/visitor.html). My application for B1 VISA is under administrative processing for two months, even in the past I have obtained B1 VISA without any administrative processing four times.

# About Conference

[The SIAM Conference on Optimization (OP23)](https://www.siam.org/conferences/cm/conference/op23) is a conference of the SIAM Activity Group on Optimization that will feature the latest research in theory, algorithms, software and applications for optimization problems
The conference will bring together mathematicians, operations researchers, computer scientists, engineers, software developers and practitioners. The conference will include:

* Invited presentations,
* Minitutorials
* Student activities, 
* Special events and workshops

# Links

* Link to my Talk: [https://meetings.siam.org/sess/dsp_talk.cfm?p=128776](https://meetings.siam.org/sess/dsp_talk.cfm?p=128776)
* Main Page of Conference: [https://www.siam.org/conferences/cm/conference/op23](https://www.siam.org/conferences/cm/conference/op23)
* Conference program: [https://meetings.siam.org/program.cfm?CONFCODE=op23](https://meetings.siam.org/program.cfm?CONFCODE=op23)
* Speaker, Organizers: [https://meetings.siam.org/speakdex.cfm?CONFCODE=op23](https://meetings.siam.org/speakdex.cfm?CONFCODE=op23)

# Abstract for FL_PyTorch 

Federated Learning (FL) has emerged as a promising technique for edge devices to collaboratively learn a shared machine learning model while keeping training data locally on the device, thereby removing the need to store and access the full data in the cloud. However, FL is difficult to implement, test and deploy in practice considering heterogeneity in common edge device settings, making it fundamentally hard for researchers to efficiently prototype and test their optimization algorithms. In this work, our aim is to alleviate this problem by introducing FL_PyTorch : a suite of open-source software written in python that builds on top of one the most popular research Deep Learning (DL) framework PyTorch. We built FL_PyTorch as a research simulator for FL to enable fast development, prototyping and experimenting with new and existing FL optimization algorithms. Our system supports abstractions that provide researchers with a sufficient level of flexibility to experiment with existing and novel approaches to advance the state-of-the-art. Furthermore, FL_PyTorch is simple to use console system, allows to run several clients simultaneously using local CPUs or GPU(s), and even remote compute devices without the need for any distributed implementation provided by the user. FL_PyTorch also offers a Graphical User Interface. For new methods, researchers only provide the centralized implementation of their algorithm.

# External Independent Assessment of FL_PyTorch

According to an external assessment carried out in the paper [FeLebrities: a user-centric assessment of Federated Learning Frameworks](https://www.techrxiv.org/articles/preprint/FeLebrities_a_user-centric_assessment_of_Federated_Learning_frameworks/21263013) our solution from user-centric perspective lies between:

* [TensorFlow Federated](https://www.tensorflow.org/federated), which is an open-source framework for machine learning and other computations on decentralized data, developed by Google.
* [FLUTE](https://www.microsoft.com/en-us/research/blog/flute-a-scalable-federated-learning-simulation-platform/), a scalable federated learning simulation platform, developed by Microsoft Research. 

---

<table>
<tr>
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/KAUST-logo.png"/> </td> 
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/siam-logo-black.png"/> </td> 
<td style="padding: 15px"> <img height="100px" src="https://burlachenkok.github.io/materials/SDAIA-Logo-2.png"/> </td> 
</tr>
</table>
