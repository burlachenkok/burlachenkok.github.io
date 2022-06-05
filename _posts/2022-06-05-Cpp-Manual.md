---
layout: post
title: C++ Manual
published: false
---
This is a post in which I would like to share complete information regarding C/C++ programming languages.

# Motivation

The C/C++ is programming language that represents pretty thin abstraction over the underlying hardware. The level below C/C++ is Assembly for your compute device.

Why compute is important is excellently motivate by prof. Charles Leiserson, MIT in his undergraduate course about Algorithms and Datastructures. I can not describe it better as he did.

Despite that some programming languages that are interpretable, has not standart for language, has no standart for for interpreter writers are due to fast learning curve are popular in some domains when the real time matters typically the interpreter is not a choise due to that:
- Interpreter provide algorithms that are 50'000 times slower then highlty optimized C/C++/ASM code
- Interpreters does not provide subtle interfaces to work with Posix API and another OS dependent API
- During work with API you don't have interface to work your memory
- The multithreading and thread syncronization implementation is pretty unobvious and maybe suboptimal
- Garbage Collector brings various limitation into the language - pointer arithmetic is disallowed in any language with GC

# Deep principles of the C++ language

Principles of language which B.Stroustroup put into the language in 1994 are still actual and the language still following it [4]. Some of them:

1. No implicit violation of static type-system
2. Provide good support for user-defined types similar to built-in types
3. The locality is good
4. Zero-Overhead principle 
  a. What you don't use - you should not pay for
  b. If something built-in in the language then it's impossible to write it better by hand

# Standarts for the Language

Both compilers writers and people who use C++ language as writers should obey the international standart ISO/IEC for the language. C++ Standardization has a long history:

1. C\+\+1998 standard -- ISO/IEC 14882-1998
2. C\+\+2003 standard -- A “bug fix release” of this standard was issued in 2003
3. C\+\+ 2011 standard -- ISO C\+\+ standard (ISO/IEC 14882-2011)
4. C\+\+ 2014 standard -- ISO C\+\+ standard (ISO/IEC 14882:2014) - completes C\+\+ 11 and fix various issues in it
5. C\+\+ 2017 standard -- ISO C\+\+ standard (ISO/IEC 14882:2017) 
6. С\+\+ 2020 standart -- ISO C\+\+ standard (ISO/IEC 14882:2020)

# Stages of processing C/C++ program

1. Processing trigrams.
2. Joining strings through the backslash character
3. Processing the program code by the preprocessor. The preprocessor can be built into the compiler, or it can be an independent program.
4. Lexical analysis of the program by splitting the program into tokens. An important part is that the compiler always tries to assemble the longest token of characters by processing the text from left to right, even if the result is an unbuildable program.  
Tokens can be separated by whitespaces. The concept of whitespace includes at compiler level things like keyboard spaces and comments.

In C++ (and in most programming languages) the tokens can be one of the following type:
a. Operators
b. Separators
c. Identifiers
d. Keywords
e. Constants

After the lexical analysis program consists of a sequence of tokens. 

https://sites.google.com/site/burlachenkok/articles/cpp_moments

# References

[1] The C ++ Programming Language Special Edition, B.Stroustrup
[2] The C Programming Language, Harbison Steel
[4] The continuing evolution of C++. Bjarne Stroustrup https://www.youtube.com/watch?v=ooehrkYkGdA
