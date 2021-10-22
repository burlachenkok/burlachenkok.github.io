---
layout: post
title: Second Semester at KAUST as CEMSE/CS Ph.D.
published: true
---

This is a post about my second semester (Spring, 2021) at KAUST.

At KAUST, classes are not big, and professors are world-level scientists.

This allows direct dialogue with professors on the subject to obtain deep insights and inspiration for the paper.

---

# Classes that I took (CS332, CS323, CS398):

As a subpart of my academic load, I took classes at KAUST during my second semester, which I can use for Ph.D. qualification requirements, and from another side, that are important for my academic work.

In this post, I would like to give some small insides about all of them.

## Federated Learning, CS 332 with prof. Peter Richtarik 

The course was taught by a professor in the CEMSE division [prof. Peter Richtarik](https://richtarik.org/) and the course are almost paper-based.

During the class, students jointly with the professor prepared high-quality lecture notes in various subjects, including information theory, local optimization methods, second-order optimization methods, software and systems for FL,
cryptography, internet of things, background materials to go deep into strong mathematical proves of various statements.

Another part of the class was targeted to create publishable work, which in my case happens. The class provides a hot start for the work.

If you're a student and want to go deep into the true multidisciplinary direction of AI, this FL can be a choice. Especially the FL fields due to its working regime (across billions of devices in cross-device setting) requires understanding what we are doing. 
Heuristics method in that field can be used as a temporary solution, but in the long term, everything should have a strict mathematical form. We probably will still have tunable parameters during modeling and connection with reality, but at least these parameters should have a decoupled form.

The course allows enough freedom to make a selection in various topics. The course has opened my eyes that preparing good lecture notes in difficult subjects in compact form is challenging.

## Deep Learning for Visual Computing, CS323 with prof. Bernard Ghannem

Even though I faced Deep Learning methods during my career at NVIDIA and during my academic passing of several classes at Stanford University, this class was very useful.

The course was taught by [prof. Bernard Ghannem](https://www.kaust.edu.sa/en/study/faculty/bernard-ghanem) from [Image and Video Understanding Lab](https://cemse.kaust.edu.sa/ivul).
At the moment of 2021, prof. Bernard Ghanem is also KAUST AI Initiative Leader and Deputy Director of AI Initiative at KAUST. This was a very pretty intensive course in terms of amount materials and homework assignments.

prof. Bernard Ghanem is similar to my advisor, prof. Peter Richtarik encourages questions and discussion during a lecture. Prof. Bernard has an optimization and signal processing background. He accurately
highlights and helps filter the interesting results from temporal heuristics that the community can not solve exactly. I think this course is beneficial for people who want to catch improvements in state-of-the-art image and video deep learning methods.

The course is a mixture of classical computer vision methods covering works from 2012 like [AlexNet](https://papers.nips.cc/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf) up to recent models, including [Transformers](https://papers.nips.cc/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf), [PointNet++](https://arxiv.org/abs/1706.02413),[ResNeSt](https://arxiv.org/pdf/2004.08955v2.pdf), [GANs](https://arxiv.org/abs/1406.2661) that can be observed as deterministic two parties game, VAE in which output of Encoder in a probabilistic way is plugged into Decoder. Nowadays, VAE is compatible with GANS, e.g., the [NVAE paper](https://arxiv.org/pdf/2007.03898.pdf).

The very good and unusual thing compared to the education model at Stanford where I took classes [CS229](https://cs229.stanford.edu/), [CS230](https://cs230.stanford.edu/) with prof. [A.Ng](https://hai.stanford.edu/people/andrew-ng) is in the following. 

Students have to read original papers and have to answer in detail and prove that they understand the scope and limitation of approaches from original papers in reading assignments. The course has opened my eyes that in Applied Machine Learning, it's far easier in 90% of cases to read original papers.
Of course, it's not always a case of considering all Applied Math in general, but in that case, it is. At Stanford classes, students have been encouraged to read original papers, but not has been strictly required.

Another special thank if to a group of amazing teaching assistants. The homework started from the first principles with using PyTorch as computation backend and simple models. Finally, somewhere in the middle, the course starts to consider pretty complicated schemas for image, video, point cloud classification.
I definitely recommend this course. 

The homework assignments were in Python using PyTorch. There would be no problem if you did not PyTorch before because Homeworks are structured pretty clearly, and in fact, one of their goals is to build your ability to use PyTorch.

If you have never used Python as language, I recommend the following materials:

* A lot of time ago, author of the language Gvino Van Rossum wrote a book. These days his book is converted into Language Tutorial: [https://docs.python.org/3/reference/index.html](https://docs.python.org/3/reference/index.html). If you have never worked with Python, please read this book. In my opinion, it's the correct way to learn a language. The book is straightforward, and it will take 5-7 days to read it.
* Once you read a book, especially if you have C/C++/ASM background, you may ask: "Where is the language standard?". The answer is, "It does not exist at all". To obtain at least some technical nuances, I recommend looking into Language Reference [https://docs.python.org/3/reference/index.html](https://docs.python.org/3/reference/index.html)
* Third good resource for finding nuances of Python programming Language is use Table of Content available here: [https://docs.python.org/3.8/contents.html](https://docs.python.org/3.8/contents.html).
* In the course, you will use a conda package manager, Jupiter notebooks, to prepare reports. These tools are very easy, and one day will be enough to figure with all of them. My random remarks about that tools: [https://sites.google.com/site/burlachenkok/python-relative-things](https://sites.google.com/site/burlachenkok/python-relative-things).

## CS398 Graduate Seminar organized by prof. Ivan Viola

Graduate Seminars is a non-credit weekly seminar in various fields connected to the CEMSE division where speakers are professors from KAUST or another university, which share their research. 
