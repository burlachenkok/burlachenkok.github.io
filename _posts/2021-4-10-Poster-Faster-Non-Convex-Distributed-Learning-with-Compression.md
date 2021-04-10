layout: post
title: Poster about Faster Non-Convex Distributed Learning with Compression
published: true
---

Poster for MARINA paper [https://sites.google.com/ucsd.edu/cedo/posters](https://sites.google.com/ucsd.edu/cedo/posters?authuser=0)

---

![Thumbnail](https://burlachenkok.github.io/materials/Marina_thumbnail.png)

# Poster session

At the Communication Efficient Distributed Optimization workshop in a TRIPODS Institute for Theoretical Foundations of Data Science, I have presented a poster about [MARINA](https://arxiv.org/abs/2102.07845), which is my joint work with  [Eduard Gorbunov](https://eduardgorbunov.github.io/), [Zhize Li](https://zhizeli.github.io/), [Peter Richtárik](https://richtarik.org/). Thank you for organizers, they have tried to simulate interactive poster session with a 2D game like platform. It was a lot of interesting posters. 

# Marina

MARINA employs a novel communication compression strategy based on the compression of gradient differences which is reminiscent but different from the technique used in the DIANA method of Mishchenko et al. (2019). All our methods are superior to previous state-of-the-art methods in terms of the oracle/communication complexity. 

# General observations
During the poster session in my booth, I have obtained the feeling that rather specialized algorithms for non-convex optimization are working with stationary points like [DIANA](https://arxiv.org/pdf/1904.05115.pdf) or [PAGE](https://arxiv.org/abs/2008.10898) has not been spread enough outside specialized groups in academia and specialized research groups in industry worked on Federated Learning. 


I suggest for all practitioners in any company they work not to forget and ask themselves two questions:

1. Does the algorithm converge in that setting?
2. If the algorithm converges, then to what does it converge?

The importance of that two questions I have learned from [prof. Brad Osgood](https://profiles.stanford.edu/brad-osgood) several years ago. They are important and was very important across different ares of Engineering and Science. 

Please take a look into convergence bounds, even they may contain not easy math. The problem is that there is an infinite number of optimization problems. And your practical situation is very likely is unique if you create something for your specific existing application. Sometimes researchers are needed to work with only experimental settings because the mathematical problem is too mystic for this moment. 

I hope that people will not overinterpret only practical papers. That aspect can be nicely described by the author of gradient boosted decision tree in that quote:
*"Here is a technic and it works better on this example, and it works better always. You should be careful - it is not true."* – [J.H. Friedman](https://statweb.stanford.edu/~jhf/), 2018
