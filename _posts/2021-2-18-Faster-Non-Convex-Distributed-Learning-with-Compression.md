---
layout: post
title:  Faster Non-Convex Distributed Learning with Compression
published: true
---

Post about the paper [https://arxiv.org/abs/2102.07845](https://arxiv.org/abs/2102.07845)

---
# About paper

The new paper: <span style="color:rgb(228,26,28)">"MARINA: Faster Non-Convex Distributed Learning with Compression"</span>, my joint work with  [Eduard Gorbunov](https://eduardgorbunov.github.io/), [Zhize Li](https://zhizeli.github.io/), [Peter Richtárik](https://richtarik.org/).

<!-- https://colorbrewer2.org/#type=qualitative&scheme=Set1&n=9 -->

# The arXiv link for the paper

[https://arxiv.org/abs/2102.07845](https://arxiv.org/abs/2102.07845)


# Abstract

We develop and analyze MARINA: a new communication efficient method for non-convex distributed learning over heterogeneous datasets. 

MARINA employs a novel communication compression strategy based on the compression of gradient differences which is reminiscent of
but different from the strategy employed in the DIANA method of Mishchenko et al (2019).

Unlike virtually all competing distributed first-order methods, including DIANA, ours is based on a carefully designed biased gradient estimator, 
which is the key to its superior theoretical and practical performance. 

To the best of our knowledge, the communication complexity bounds we prove for MARINA are strictly superior to those of all previous first-order methods. 

Further, we develop and analyze two variants of MARINA: VR-MARINA and PP-MARINA. 

The first method is designed for the case when the local loss functions owned by clients are either of a finite sum or an expectation form, 
and the second method allows for partial participation of clients – a feature important in federated learning. 

All our methods are superior to previous state-of-the-art methods in terms of the oracle/communication complexity. Finally, we provide a convergence analysis of all methods for problems satisfying the Polyak-Lojasiewicz condition.

