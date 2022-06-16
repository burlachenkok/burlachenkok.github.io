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

# Preprocessor

C++ 1998 and 2003 uses the C89 preprocessor, although the C language has undergone changes: Tradition C, C89, C95, C99, C11.

# Names Overloading

In C and other programming languages as well, the same identifier can be associated with more than one object at a time. This situation is called *name overloading* or *name hiding*.
In C++ (Take look for example C++ 2003 Standart, chapter 13), this concept is introduced as in C language. It is an error to create two declarations of the same name in the same overload class in the same visibility block or at the top level.

| # | ** Overloading class name**       | ** Identifiers included in the class**                                                                         |
|---|-----------------------------------|----------------------------------------------------------------------------------------------------------------|
| 1 | Preprocessor Macro Names          | The names used by the preprocessor are independent  of any other identifiers                                   |
| 2 | Operator labels/tags              | The labels used immediately follow the goto statement                                                          |
| 3 | Structures, Union, and Enums tags | They are part of a structure, union, or enumeration,  and immediately follow the keywords: struct, union, enum |
| 4 | Components namespace              | Defined in the namespace(or name scope) associated with  the corresponding structure or union type             |
| 5 | Another namespace                 | Name of the following objects: * Variables * Functions * Typedef names * Enumeration constants                 |

C++ introduces structure and union tags and enumeration names implicitly declared via typedef in the namespace "another" where in fact there are also usual variables are locating.

However, these identifiers (tag names) can be hidden by subsequent variable or function declarations, or by an enumeration member of the same name in the same scope. 
If you explicitly use a typedef for a structure followed by a variable declaration, it will lead to an error.
It is very interesting that according to ISO/IEC 14882 C++ 2003, 3.3.7. In any order, functions/variables take precedence over type tags.

# About used memory for types

The representation of an object in memory is a sequence of bits. The representation does not have to include all the *bits*, but the size of an object is the number of units of memory that it occupies. 
The amount occupied by one char character is taken as a memory unit. The number of bits in a character is specified in the CHAR_BIT macro in C Language. All objects of the same type by C/C++ rules occupy the same amount of memory.

Computers are classified into two categories in the order of bytes in a word:
- Right to left, or Little - Endian -- the address of a 32-bit word matches the address of its least significant byte (Example of CPU architectures are Intel x86, Pentium)
- From left to right, or Big - Endian -- the address of a 32-bit word matches the address of its high-order byte (Motorolla)

Some systems support two modes at the same time. In some computers, data can be located in memory at any address, in others, alignment conditions are imposed on certain types.

A typical data type to store pointers to some object/data is a pointer. To store (or serialize the value of pointer) in some integer variable, you can use intptr_t. 
The intptr_t integer type was introduced in C99, uintptr_t is sufficient to store a pointer to any data, but formally not to a function.
There is a special value in C/C++ called a null pointer that is equal to a null pointer constant. A null pointer can be converted to any other type of pointer.

# Literal constants

In C/C++ in a literal expression, you can encode the type of a constant:

| # | **Type**      | **Suffix** | **Alternative suffix** |
|---|---------------|------------|------------------------|
| 1 | long          | l          |                        |
| 2 | long long     | ll         | LL                     |
| 3 | unsigned      | u          | U                      |
| 4 | unsigned long | ull        | ULL                    |
| 5 | float         | f          | F                      |
| 6 | double        | no suffix  |                        |
| 7 | long double   | l          | L                      |

# Built-in type conversion

Before go into technical details about type conversion, let me be honest - it's hard to remember them, so possibly it is better to observe the big picture first:
*The general requirement when converting integer types is the mathematical equivalence of the source and target values.*

Now let's go into sublt technical details.

## Prohibited conversions

1. Converting a pointer to a function to a pointer to a data and to the other side direction is not allowed in C/C++
2. Built-in conversion to a struct, the union is not allowed.
3. C++ treats enum as distinct from each other and from integer type as well.
4. In C and C ++ implicit conversion from enumerated types to integer types are allowed.
5. In C implicit conversion from integer to enumerated types is also allowed because in C enum are C, but in C++ it is prohibited.
6. Converting a pointer to a function to a pointer to a data and to the other side too - is not allowed in C++


## The sequence of type conversions rules in C/C++
1. Trivial transformation. Conversion to identical types. A conversion from "function ..." to "function pointer ...."
2. If an overflow occurs during conversion to a signed type, then the value is considered overflowed and technically undefined.
3. If an overflow occurs during conversion to an unsigned type, then the final value is equal to the "unique value" mod $$2^n$$ of the result. When using two's complement presentation, converting to/from signed to unsigned integers of the same size does not require any bit change.
4. If the final type is shorter than the original and both types are unsigned, the conversion can be performed by discarding the appropriate number of most significant bits. The rule is also applicable to integer types in 2-s complement notation.
5. When converting from float values to int, the final value should be equal to the initial value if possible. The nonzero fractional part is discarded. 
(The result is undefined if the value cannot even be approximated.)

6. In C, conversion to floating-point types is possible only from arithmetic types. In the case of conversion from double to float, the final value must be equal to one of the two values closest to the original value. 
(The choice of rounding is implementation-dependent.)

7. If it is impossible to convert from double or int to float.
(If the range of the target double type does not match, then the value is undefined.)
8. Conversion from the type array of type T to a pointer to type T is performed by substituting the pointer to the first element of the array.
9. A value of any type can be converted to void
10. Conversion to void * and back guarantee the restoration of the original pointer value
11. In C, void * can be implicitly converted to a pointer to any type. In C++, an explicit cast is required. (Annex C, 4.10, C ++ 2003 standard)
12. On the operands of unary operations, ordinary unary conversions are performed. The goal is to reduce the number of arithmetic types.
   * An array of type T => pointer to the first element (not applied for & operator and for sizeof operators)
   * Function => function pointer
   * Conversions from an integer type of rank below int => to int
   * Conversions from unsigned integer types lower than int, int represent all values => values are cast ​​to integers
   * Conversions from unsigned integer types lower than int, but int does not represent all => values are cast ​​to unsigned int

13. On the operands of a binary operation, the usual unary conversions of are performed separately for each, and then the usual binary conversions.
14. If someone of operand of binary operator is the type long double, double, float, in the second rank lower, then it is cast to the type with highest rank.
15. If both operands are unsigned, then both are cast to a higher rank unsigned type.
16. If both operands are signed, then both are cast in the signed type of the higher rank.
17. Unsigned operand and lower-ranked signed operand => unsigned type.
18. Unsigned operand and signed type operand of higher rank => signed type.
19. If the prototype is controlled by an ellipsis (...), i.e. function obtain varying argument number, then the usual unary conversions are performed on the operands. Also float is always converting to double.
    (If there is no ellipsis and the call is fully prototype driven, then float is not converting into double)

# Namespaces

The namespace is a mechanism for reflecting logical grouping. If some declarations can be combined according to some criteria, they can be placed in the same namespace to reflect this fact. 

Namespace advantages:
* Logical structure reflection
* Avoidance of name conflicts
* Express a coherent set of tools 
* Prevent users from accessing unnecessary tools 
* Do not require significant additional effort when using

Namespace aisadvantages:
* Waste of time analyzing the assignment of objects to different namespaces
* Various additional nuances: 
- A local variable or a variable declared via using hides external variables in relation to the block of visibility.
- When libraries that declare many names are made available through the using directive, it is important to understand that unused name conflicts are not considered errors.
- Elements of the same namespace can be in different files.

# New operator (memory allocation)

In C++, before the introduction of the exception mechanism, the new operator returned 0 when the memory allocation failed. 
In the C++ standard, new by default throws a bad_alloc exception. As a rule, it is best to strive for similarity to the standard. Better to modify the program to catch bad_alloc rather than check for 0. 

In both cases, doing anything other than throwing an error message is not easy on most systems. See paragraph 5.3.4. Subparagraph 13. http://www.ishiboo.com/~nirva/c++/C++STANDARD-ISOIEC14882-1998.pdf

For Visual Studio compiler: 
1. new (std :: nothrow) - does not throw an exception 
2. regular new - throws an exception you can customize the behavior using linker options http://msdn.microsoft.com/en-us/library/kftdy56f.aspx


# Exceptions

When a program is constructed from separate modules, and especially when these modules are in independently separate libraries, it is convenient to divide error handling into two parts:
* Generation of information about the occurrence of an error situation that cannot be resolved locally
* Handling Errors Found Elsewhere

Error handling code can be shorter and more elegant by using a return value, but this solution does not scale well.

Generally, separating error handling code from "normal" code is a good strategy. Throwing an exception may leave the object in an invalid state.

Throwing an exception can be a source of memory and other resource leaks. It's best to rely on the properties of constructors and destructors and their interactions with exception handling to deal 
properly with an object. (Escape from a block by throwing an exception cleans up all created local automatic objects in reverse order of creation.). Writing correct exception-safe code using explicit try can be a difficult task.


## Notes about use exceptions:

* You can group exceptions by inheritance relation
* Exceptions at the time of generation are copied. The const modifier in the catch block does not affect anything. However, the presence of a T& or T type signature is affected. The latter causes the copy constructor to execute. For throw T() , you can't see the copy constructor run in VS 2012. Can be seen for {T e; throw e;}
* It is possible to rethrow an exception.
* When an exception is thrown in a constructor, the object's destructor is not called.
* If an exception is thrown in the destructor during the call to the destructor during exception handling, then this is considered an error in the exception handling mechanism and std::terminate() is called. 
To distinguish behavior, you can use the uncaught_exception () call in the destructor

* Exiting a destructor by throwing an exception is against the requirements of the standard library.
* If an exception is thrown but not caught, std::terminate is called. You can set your behavior with set_terminate.
* The process of calling destructors for automatic objects constructed on the path from a try block to a throw-expression is called “stack unwinding.” 
* If a destructor called during stack unwinding exits with an exception, terminate is called (15.5.1). So destructors should generally catch exceptions and not let them propagate out of the destructor.
* The basic errors classes are std::exception, std::logic_error, std::runtime_error. Some others classes: bad_alloc, bad_cast, bad_typeid, bad_exception, out_of_range, invalid_argument, overflow_error, ios_base::failure
* If a function tries to throw an exception it didn't declare it will result in a call to std::unexpected which by default pulls std::terminate (p.429, Stroustrup, special edition)

```cpp
intf(); /* Can throw any exception */
int f() throw(); /* Throw no exceptions */
int f() throw(x2, x3); /* Throws only exceptions x2, x3 */
```

https://sites.google.com/site/burlachenkok/articles/cpp_moments

# References

[1] The C ++ Programming Language Special Edition, B.Stroustrup
[2] The C Programming Language, Harbison Steel
[4] The continuing evolution of C++. Bjarne Stroustrup https://www.youtube.com/watch?v=ooehrkYkGdA
