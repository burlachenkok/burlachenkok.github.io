---
layout: post
title: Poster about Faster Non-Convex Distributed Learning with Compression
published: true
---

About poster for [MARINA paper](https://arxiv.org/abs/2102.07845) presented at [Poster session](https://sites.google.com/ucsd.edu/cedo/posters)

---

![Thumbnail](https://burlachenkok.github.io/materials/Marina_thumbnail.png)

# Poster session

At the Communication Efficient Distributed Optimization workshop in a TRIPODS Institute for Theoretical Foundations of Data Science, I have presented a poster about [MARINA](https://arxiv.org/abs/2102.07845), which is my joint work with  [Eduard Gorbunov](https://eduardgorbunov.github.io/), [Zhize Li](https://zhizeli.github.io/), [Peter Richtárik](https://richtarik.org/). Thank you for the organizers, they have tried to simulate interactive poster sessions with a 2D game-like platform. It was a lot of interesting posters. 

Copy of my moster is locating here: [MARINA_Poster_07APR2021](https://burlachenkok.github.io/materials/MARINA_Poster_07APR2021.pdf)

# Marina

MARINA employs a novel communication compression strategy based on the compression of gradient differences which is reminiscent but different from the technique used in the DIANA method of Mishchenko et al. (2019). All our methods are superior to previous state-of-the-art methods in terms of the oracle/communication complexity. 

# General observations
During the poster session in my booth, I have obtained the feeling that rather specialized algorithms for non-convex optimization are working with stationary points like [DIANA](https://arxiv.org/pdf/1904.05115.pdf) or [PAGE](https://arxiv.org/abs/2008.10898) has not been spread enough outside specialized groups in academia and specialized research groups in the industry worked on Federated Learning. 

No matter in what aspect of Science we're working - I suggest for all practitioners in any company they work not to forget and ask themselves two questions:

1. Does the algorithm converge in that setting?
2. If the algorithm converges, then to what does it converge?

The importance of that two questions I have learned from [prof. Brad Osgood](https://profiles.stanford.edu/brad-osgood) several years ago. 
Please not forget about them, and if you have never asked yourself start do it.