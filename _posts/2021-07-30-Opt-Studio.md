---
layout: post
title: Opt-Studio (mini PyTorch) - Shell, Plotter, BLAS in C++
published: true
---
This is a project created as a final project at [King Abdullah University of Science and Technology](https://cemse.kaust.edu.sa/) for the course
[CS 380 GPU and GPGPU Programming, 2020, Fall](https://faculty.kaust.edu.sa/sites/markushadwiger/Pages/CS380.aspx). 

Links:
* [Project location](https://bitbucket.org/konstantin_burlachenko/opt_studio/)
* [Autogenerated Doxygen documentation](https://bitbucket.org/konstantin_burlachenko/opt_studio/src/master/docs/optimization_studio.chm)

# Motivation 

Method of optimization has a long history and in someway they have formed a field of Applied Mathematics. The motivation was to assist researchers to create new algorithms which may be more near to the hardware metal, and decrease the lag time once algorithms come into  products, typically written in C++. This project is a small step to provide need infrastructure in C++ language.

# Computation
We live in an era when computation assists in the development of different fields. People create specific general-purpose or DSL languages like Matlab, R, Python.

What is circular is that all programming languages infrastructure for Matlab, R, Python, Java, C# is developed in C++. In some sense, these are only an extra level of abstraction. If think completely freely in my opinion it's time to forget to some extent about Matlab, R, Python as not necessary level.

We can think about Matlab is a domain-specific language for Mathematic. But in 21 century each area of Mathematics is so developed that it requires separate treatment at a fundamental level with computation support. B.Stroustroup put into C++ language in 1994 the following deep principles:

----

a. No implicit violation of static type-system. Work with user types so effectively as with built-in things.
b. What you don't use - you should not pay for.
c. If something built-in in the language then it's impossible to write it better by hand

----

Unfortunately C++ is pretty low level language.

# Components

## Shell
Project has an interactive shell like a Python interpreter (or BASH, or R) which allow manipulation with variables and expressions. Shell allows take a look into available variables (vectors, matrices, scalars) and print it (similar to Matlab, R studio), differentiate numerically algebraic expressions.

## Formulas plotter
It's possible to visualize expressions (formulas) that represent explicit functions in form of Y=F(X), where F is constucted with the availble algebraic expressions.

## Graph plotter
There is an extra plotter tool which allows obtaining information from the shell remotely via TCP/IP. It's locating in a separate repository: https://github.com/burlachenkok/plotter_plusplus.
In Framework there is a need abstraction to send data over TCP/IP network.

## Framework

Internal infrastructure of the project allows working with filesystem, network, regular expression, serializing into the filesystem, and a various day-to-day thing which is absent mostly by design in C++.

# Credits and references
Original author: Konstantin Burlachenko. Email: konstantin.burlachenko@kaust.edu.sa