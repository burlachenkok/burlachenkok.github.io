---
layout: post
title: OpenSource KD tree implementation
published: true
---

This is a post about Open-source KD tree implementation.

---
# Introduction

This is a post dedicated to give a small comment about implementation of KD-tree way for space partitioning (also known as spatial indexing) available at:
[https://github.com/burlachenkok/lw_index_datastructs](https://github.com/burlachenkok/lw_index_datastructs)



This algorithm proposed by Jon Bentley when he undergraduate student from Stanford under the supervision of Donald Knuth. In this [video](https://www.youtube.com/watch?v=8hupHmBVvb0) Jerome Friedman at 2004 remembers his work with the work of Jon Bentley.

----
# Thoretical Speed

KD trees allow todo Insert/Search/Delete points in Euclidian space ($$R^d$$) typically in ~lg(N) iterations. At each iteration:

* You compare specified coordinate O(1)
* You evaluate L2 norm or another norm. So if take into account "d" and evaluate L2 norm just usually it will take O(d) single operations
* But both this two numbers in case of small d < lg(N) can be hidden into O(1)

Range Count / Range search.
Find all "R" points from all "N" points that lie in a specific range in which is typical: **~R+lg(N)**,
But the worst case is: **~R+$$N^{0.5}$$**

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

But KD tree generalizes for a higher dimension and this implementation supports it. Based on my knowledge from Datamining lectures [CS246](http://web.stanford.edu/class/cs246/) from prof. Jure Leskovec in high dimensional space is almost true that everything is very far from everything so if you choose of using for **K Nearest Neighbors**
[https://sites.google.com/site/burlachenkok/k-nearest-neighbors-and-things-around-it](https://sites.google.com/site/burlachenkok/k-nearest-neighbors-and-things-around-it) and you choose for distance function or dissimilarity metric is based on Eculidan norm in $$R^d$$ then this library will help you for your C++ implementation.
