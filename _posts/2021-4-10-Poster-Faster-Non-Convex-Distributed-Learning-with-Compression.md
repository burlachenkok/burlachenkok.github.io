---
layout: post
title:  Poster about Faster Non-Convex Distributed Learning with Compression
published: true
---

This is a post about poaster for MARINA paper [https://sites.google.com/ucsd.edu/cedo/posters](https://sites.google.com/ucsd.edu/cedo/posters?authuser=0)

---

# About poster session

At the Communication Efficient Distributed Optimization workshop in a TRIPODS Institute for Theoretical Foundations of Data Science, I have presented a poster about [MARINA](https://arxiv.org/abs/2102.07845). This is my joint work with  [Eduard Gorbunov](https://eduardgorbunov.github.io/), [Zhize Li](https://zhizeli.github.io/), [Peter Richtárik](https://richtarik.org/).

MARINA employs a novel communication compression strategy based on the compression of gradient differences which is reminiscent, but different from the strategy employed in the DIANA method of Mishchenko et al (2019). All our methods are superior to previous state-of-the-art methods in terms of the oracle/communication complexity. 

During the poster session, I have obtained the feeling that rather specialized algorithms for non-convex optimization which are working with stationary points like [DIANA](https://arxiv.org/pdf/1904.05115.pdf) or [PAGE](https://arxiv.org/abs/2008.10898) are not well known. There are a lot of optimization algorithms and I suggest for practitioners ask themselves 2 questions:
1. Does the algorithm converge in that setting?
2. If the algorithm converges then to what does it converge?

The importance of the first two questions I have learned from [prof.Brad Osgood](https://profiles.stanford.edu/brad-osgood) several years ago. Another aspect please take a look into convergence bounds, evn they may contain not easy math. The problem is that there is an infinite amount of instances of optimization problems each one corresponds to your unique situation. And your practical situation is very likely is unque if you create something. 
Sometimes researchers are needed to work with only experimental settings because the mathematical problem is too mystic for this moment in time. This is fine. But please does not overinterpret only practical papers. There is unfortunately a *hidden devil* in them which I think can be nicely described by the author of gradient boosted decision tree in that quote:

*"Here is a technic and it works better on this example and it works better always. You should be careful. It’s not true."* – [J.H. Friedman](https://statweb.stanford.edu/~jhf/), 2018
