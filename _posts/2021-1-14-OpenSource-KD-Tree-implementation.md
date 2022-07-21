---
layout: post
title: OpenSource KD tree implementation.
published: true
---

Post about my Open-Source KD tree implementation.

---
# Introduction

This is a post dedicated to giving a small comment about the implementation of the KD-tree way for space partitioning (also known as spatial indexing) available at:
[https://github.com/burlachenkok/lw_index_datastructs](https://github.com/burlachenkok/lw_index_datastructs)



This algorithm was proposed by Jon Bentley when he was an undergraduate student at Stanford under the supervision of Donald Knuth. Today, it's a very suitable algorithm for indexing structures used in Database Management Systems, Graphics, Games, Visualization, Physics simulation, etc. In this [video](https://www.youtube.com/watch?v=8hupHmBVvb0), prof. Jerome Friedman 2004 remembers that his work intersects in terms of motivation with the work of Jon Bentley.

----
# Thoretical computation demand

KD trees allow todo Insert/Search/Delete points in Euclidian space ($$R^d$$) typically in $$~\log(N)$$ iterations. At each iteration:

* You compare specified coordinate $$\mathcal{O}(1)$$
* You evaluate $$L_2$$ norm or another norm and perform search pruning based on exploiting properties of the norm (See implementation). So if we take into account dimension $$d$$ to evaluate $$L_2$$ norm of a vector, then usually (if not exploit some other properties), it will take $$\mathcal{O}(d)$$ single operations
* But both these two numbers in case of $$d < \log(N)$$ can be hidden into $$\mathcal{O}(1)$$

# Range Count / Range search.
Find all $$R$$ points from all $$N$$ points that lie in a specific range  typically costs $$\sim R+\log(N)$$, but the worst case is: $$\sim R+N^{0.5}$$

----
# Applications


Classical applications are everywhere where we use geometric data:

1. Ray-tracing
2. 2d range search
3. Collision detection
4. Nearest neighbors search, etc
5. n-body simulation algorithm
6. Search in databases
7. Computer Graphics

But KD tree generalizes for a higher dimension, and this implementation supports it. Based on my knowledge from Datamining lectures [CS246](http://web.stanford.edu/class/cs246/) from prof. Jure Leskovec in high dimensional space is almost true that everything is very far from everything, so if you choose to use for **K Nearest Neighbors**
[https://sites.google.com/site/burlachenkok/k-nearest-neighbors-and-things-around-it](https://sites.google.com/site/burlachenkok/k-nearest-neighbors-and-things-around-it) and you choose for distance function or dissimilarity metric is based on Eculidan norm in $$R^d$$ then this library will help you for your C++ implementation (if C++ is your choice).
