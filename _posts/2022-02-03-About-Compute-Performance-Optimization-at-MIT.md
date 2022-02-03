---
layout: post
title: Performance Engineering course at 6.172 at MIT
published: true
---

This is a post about the advanced course "6-172" at MIT and usefull materials for anybody who optimize code performance.

---

The advanced course [Performance Engineering of Software Systems](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/index.htm) provides 
various exciting insights on optimizing the performance of code dedicated for the execution in general-purpose CPU processors. The published materials contains [slides](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/) and [video of lectures](https://www.youtube.com/playlist?list=PLUl4u3cNGP63VIBQVWguXxZZi0566y7Wf).

This course is not about compilers or applying some contemporary math areas for improving performance but about improving algorithm performance in real hardware. It is about constants that are hidden in the complexity of algorithms.

The main prof. in the course was [Charles E. Leiserson](https://en.wikipedia.org/wiki/Charles_E._Leiserson), co-author of the classical book [Introduction to Algorithms](https://www.amazon.com/Introduction-Algorithms-3rd-MIT-Press/dp/0262033844).

There are a lot of useful materials, and all lectures are interesting. But I would like to bring some insights about several of them:

[Lecture 1](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/MIT6_172F18_lec1.pdf) presented a path on how to implement and to even beat [Intel MKL](https://en.wikipedia.org/wiki/Math_Kernel_Library) library for dense matrix multiplication in fp32 on square matrices with 4096 x 4096 elements.
The lecture demonstrated that standart Python interpreter (CPython) is 51497 slower than highly optimized C code, and standart JAVA platform with is only 5000 slower than C. Table from Lecture-1 with speed comparision of implementations is presented below:
<table>
<tr><td> <img width="100%" src="https://burlachenkok.github.io/images/blas_compare_speed_of_impl.png"/> </td></tr>
</table>

This is coincident with that Bjarne Stroustrup have mentioned in 2017 [https://youtu.be/fX2W3nNjJIo?t=558](https://youtu.be/fX2W3nNjJIo?t=558) at 09:20:

*"People select the simplest thing to pick up and it's Python..And then they are out of CPU power..I heard about biologists who run a 3-month run, it could be done in 10 minutes. And we know it because it was done when we can not wait for 3 months anymore.."*

Speedup from that experiment that B.Stroustrup has mentioned in 2017 after moving to C++ from Python is the following: 3*30*24*60/10=12960.

[Lecture 2](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/MIT6_172F18_lec2.pdf) summarize John Bentley rules invented from 1990 for the current area. It contains suggestions for improving data structures, loops, logic, functions.

[Lecture 3](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/MIT6_172F18_lec3.pdf) present several specific Bit Haks tricks that sometimes allow eliminating branches in the code. Sometimes the compiler does not optimize, and you have to do it yourself by hand.

[Lecture 4](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/MIT6_172F18_lec4.pdf) and [Five lecture](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/MIT6_172F18_lec5.pdf) present several things about how a computer works. And for people aware of System Programming and how the computer is working can skip that.

[Lecture 10](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/MIT6_172F18_lec10.pdf) was about accurate measurement time for algorithms.

[Lecture 11](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/MIT6_172F18_lec11.pdf) brings strategies for implementing heap allocation (Fixed-size allocation using free lists, Variable-sized allocation using binned free lists) and garbage collector (mark-and-sweap) and (stop-and-copy)

Another lecture covers topics such: as threads, caches, races, etc.
What makes this material pretty unique is the fact that it contains real examples of how to improve real algorithms. Unfortunately, a lot of books on such a level of granularity in computing systems do not provide any examples. 

[Lecture 18](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/MIT6_172F18_lec18.pdf) was a guest talk from prof. [Saman Amarasinghe](https://people.csail.mit.edu/saman/). He gave a lecture where he covered a bit all systems that (it seems) he co-developed with his peers:

* GraphIt  [https://people.csail.mit.edu/jshun/graphit.pdf](https://people.csail.mit.edu/jshun/graphit.pdf)
* Halide    [https://people.csail.mit.edu/jrk/halide-pldi13.pdf](https://people.csail.mit.edu/jrk/halide-pldi13.pdf), [https://halide-lang.org/](https://halide-lang.org/)
* OpenTuner [https://ieeexplore.ieee.org/document/7855909](https://ieeexplore.ieee.org/document/7855909)

During the lecture prof. Saman Amarasinghe has mentioned that:

* [YouTube](https://youtube.com/) processes each video with Halide at input stage
* Adobe Photoshop is rewritten into Halide

[GraphIt](https://people.csail.mit.edu/jshun/graphit.pdf) is a DSL language that allows tuning real performance for graph algorithms, where algorithms need to be implemented at the low-level/metal level.

Another exciting guest lecture was [Lecture 21](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-172-performance-engineering-of-software-systems-fall-2018/lecture-slides/MIT6_172F18_lec21.pdf) with Jon Bentley, who during being D.Knuth student invented KD-trees.
In his talk [https://www.youtube.com/watch?v=SS5KfIFzfEE](https://www.youtube.com/watch?v=SS5KfIFzfEE), Jon Bentley shows how to make not-empirical Travel Salesman Problem(TSP) workable (typically for) in 40-50 cities, where distance is Euclidian distance in the 2D plane with using various pruning and software optimization tricks.
