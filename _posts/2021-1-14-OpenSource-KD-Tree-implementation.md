---
layout: post
title: OpenSource KD tree implementation
tags: markdown jekyll mathjax latex
published: true
---

This is a post about Open-source KD tree implementation.

---
# Introduction

Inline math $f(x)=x^2$

This is a post dedicated to give a small comment about implementation of KD-tree way for space partitioning (spatial indexing) available at:
https://github.com/burlachenkok/lw_index_datastructs

This algorithm proposed by Jon Bentley when he undergraduate student from Stanford under supervision of Donald Knuth. In this [video](https://www.youtube.com/watch?v=8hupHmBVvb0) Jerome Friedman at 2004 remembers about his work with work of Jon Bentley.

----
# Thoretical Speed

KD trees allows todo Insert/Search/Delete points in Euclidian space ($$R^d$$) typically in ~lg(N) time.

Range Count / Range search.
Find all "R" points from all "N" points that lie in a specific range in which is typical: **~R+lg(N)**,
But worst case is: **~R+$$N^{0.5}$$**

----
# Applications


Classical applications is everywhere where we use geometric data:

1. Ray-tracing
2. 2d range search
3. Collision detection
4. Nearest neighbors search, etc
5. n-body simulation algorithm proposed by Anrew Appel
6. Search in databases
7. Computer Graphics

But KD tree generalizes for higher dimension and this implementation supports it. Based on my knowledge from Datamining lectures (http://web.stanford.edu/class/cs246/) from prof. Jure Leskovec in high dimensional space is almost the true that every thing is very far from everything so if you choice of using for **K Nearest Neighboors**
(https://sites.google.com/site/burlachenkok/k-nearest-neighbors-and-things-around-it) and you choice for distanceFunction or dissimilarity metric is based on Eculidan norm in $$R^d$$ then this library will help you for your C++ implementation.
