---
layout: post
title: C++ Manual
published: false
---

This is a long post in which we would like to share complete information regarding C and C++ programming languages.

The C++ has been created
# Motivation`

The C/C++ programming language represents a pretty thin abstraction over the underlying hardware. The level below C/C++ is Assembly for your computing device.

Why computing is critical is excellently motivated by prof. Charles E. Leiserson, MIT, in his undergraduate course about Algorithms and Data structures. We can not describe it better as he did. 

If you want to learn about that please look into his lectures MIT 6.046J / 18.410J Introduction to Algorithms (SMA 5503), Fall 2005, publicly available.

Nowadays, in 2022, for some reason, interpretable programming languages are in fashion. We think that is primarily due to the fast learning curve and secondary because the heavy design of computing science systems goes into the past in the pretty dynamic world in which we are. 

Nevertheless, In some domains, the interpreter is not a choice when actual time matters.  

In general, we think the main problem with interpreters is the following:

- Interpreters provide algorithms that are 50'000 times slower than highly optimized C/C++/ASM code. The interpreter typically parsed the program's text line by line (that represented or in text form or extremely high-level instructions).

- Interpreters do not provide subtle interfaces to work with POSIX API and other OS-dependent APIs.
- During work with an interpreter, you don't have an interface to work your memory.
- The multithreading and thread synchronization implementation is pretty unobvious and may be suboptimal in the interpreter. (E.g., you can look into GIL in Python)
- Garbage Collector brings various limitations into the language - Pointer arithmetic is disallowed in any language with GC
- There are some subtleties with implementing function call (or method call) in some specific hardware. The function calls It's effective.
- Finally, the implementation of an interpreter is very likely just a collection of C/C++ libraries wrapped up into the program that can execute the command and therefore called an interpreter.
- The absence of compiler makes handling problems in the code to be testable without compiler. It has pros. - you do not spend time for compilation, but there are cons. - now compiler will not tell you about errors in the code, because there is no compiler.

The interpreter is great for prototyping, and sometimes it is enough. But any interpreter, any algorithm in it, can be beaten by C++/ASM implementation. So at least be aware of that.

Some language decision:

- C++ does not have a universal class Object. It's so beucase in C++ we don't need one: generic programming provides statically type safe alternatives in most cases. Also there is no useful universal class, and in fact using a universal base class implies cost

- Template are not Generics (from C# or Java). Generics are primarily syntactic sugar for abstract classes. That is, with generics (whether Java or C# generics), You program against precisely defined interfaces and typically pay the cost of virtual function calls and/or dynamic casts to use arguments.

# Deep principles of the C++ language

Principles of language which B.Stroustroup put into the language in 1994 are still current, and the language still follows them [4]:

1. No implicit violation of static type-system.
2. Provide good support for user-defined types similar to built-in types.
3. The locality is good.
4. Zero-Overhead principle:
    
    a. What you don't use - you should not pay for.
    
    b. If something is built-in in the language, it's impossible to write it better by hand.

# Standarts for the Language

Both compilers writers and people who use C++ language as writers should obey the international standard ISO/IEC for the language. C++ Standardization has a long history:

1. C\+\+1998 standard - ISO/IEC 14882-1998
2. C\+\+2003 standard - A "bug fix release" of this standard was issued in 2003
3. C\+\+ 2011 standard - ISO C\+\+ standard (ISO/IEC 14882-2011)
4. C\+\+ 2014 standard - ISO C\+\+ standard (ISO/IEC 14882:2014) - completes C\+\+ 11 and fix various issues in it
5. C\+\+ 2017 standard - ISO C\+\+ standard (ISO/IEC 14882:2017) 
6. С\+\+ 2020 standard - ISO C\+\+ standard (ISO/IEC 14882:2020)

To be honest with you, we don't know how is it possible to write compilers or write programs without standard of the language.

# C++ from point of view of author of that programming Language (B. Stroustroup)
Barge Stroustrup in 2010 jokingly describes C++ as a language:
1. Support generic programming
2. Hybrid language
3. Multi-paradigm programming Language
4. Buffer Overflows
5. Too Big
6. Object-Oriented-Programming Language
7. Low level
8. Embedded system language
9. Random Collections of features
10. It's C!

# C++ guarantees
Fundamental types of C++ code guarantees:
1. **Basic Guarantee** - no leaks and standard libraries supported.
2. **Strong Guarantee** - whether the operation is completed.

All containers in C++98 provide a fundamental guarantee. And some operations (for example, `std::vector<T>::push_back`) give a Strong Guarantee.

# Stages of processing C/C++ program

1. Processing trigrams.

2. Joining strings through the backslash character.

3. Processing the program code by the preprocessor. The preprocessor can be built into the compiler, or it can be an independent program.

4. Lexical analysis of the program by splitting the program into tokens. An important part is that the compiler always tries to assemble the longest token of characters by processing the text from left to right, even if the result is an unbuildable program.

Tokens can be separated by white spaces. The concept of whitespace includes things like different keyboard spaces and comments at compiler level.

In C++ (and in most programming languages) the tokens can be one of the following types:

a. Operators

b. Separators

c. Identifiers

d. Keywords

e. Constants

After the lexical analysis program consists of a sequence of tokens. 

# Preprocessor

C++ 1998 and C++2003 uses the C89 preprocessor, although the C language has undergone changes: Tradition C, C89, C95, C99, C11.

Preprocessor macro extensions in C/C++ has the following property. Once a macro call is replaced by an extension, the macro call search process starts from the beginning of the expanded extension for further replacement.

During this process, macros that are referenced in their own expansion are not re-expanded and that preprocessor macro extension does not lead to infinite recursion.
`#define sqrt(x) (x<0 ? sqrt(x) : sqrt(-x))`

# Some general rules of C/C++

* Names starting with a double underscore (__) or an underscore followed by an uppercase letter (e.g., _Foo) are reserved by the compiler implementations.

* In C and in C++, if you read a variable twice in an expression where you also write it, the result is undefined. 

* For C/C++ preprocessor any undefined identifiers that appear after the conditional directives `#if` and `#elif` are replaced
with the number 0.


# What is impossible in C/C++

* *Address iniduvual bits*. Few machines can directly address an individual bit. Even if the machine allows to do it - then it is out of the scope of C/C++, to be honest. (Of course - you can operate on bits, but not directly)

* *Define you own operators.* B.Stroustroup said that the possibility has been considered several times, but each time he/they decided that the likely problems outweighed the likely benefits.


# Names Overloading

In C and other programming languages as well, the same identifier can be associated with more than one object at a time. This situation is called *name overloading* or *name hiding*.
In C++ (Take look for example C++ 2003 Standard, chapter 13), this concept is introduced as in C language. 

It is an error to create two declarations of the same name in the same overload class in the same visibility block or at the top level.

| # | **Overloading class name**       | **Identifiers included in the class**                                                                         |
|---|-----------------------------------|----------------------------------------------------------------------------------------------------------------|
| 1 | Preprocessor Macro Names          | The names used by the preprocessor are independent of any other identifiers.                |
| 2 | Operator labels/tags              | The labels used immediately follow the `goto` statement.                                                          |
| 3 | Structures, Union, and Enums tags | They are part of a structure, union, or enumeration, and immediately follow the keywords: ```struct```, ```union```, ```enum```. |
| 4 | Components namespace              | Defined in the namespace(or name scope) associated with  the corresponding structure or union type.             |
| 5 | Another namespace                 | Name of the following objects: *Variables*, *Functions*, *Typedef names*, *Enumeration constants*.                 |

C++ introduces structure and union tags and enumeration names implicitly declared via `typedef` in the namespace "Another" where in fact there are also usual variables are locating.

However, tag names can be hidden by subsequent variable or function declarations, or by an enumeration member of the same name in the same scope. 
If you explicitly use a ```typedef``` for a structure followed by a variable declaration, it will lead to an error.

It is very interesting that according to ISO/IEC 14882 C++ 2003, 3.3.7. In any order, functions/variables take precedence over type tags.

# Used memory for types and its layout

1. The representation of an object in memory is a sequence of bits. The representation does not have to include all the *bits*, but the size of an object is the number of units of memory it occupies. 
The amount occupied by one char character is taken as a memory unit. The number of bits in character is specified in the CHAR_BIT macro in C Language. All objects of the same type by C/C++ rules occupy the same amount of memory. In practice, however, one char is "always" one byte, i.e., the 8 bits number.

2. Computers are classified into two categories in the order of bytes in a word:
- *Right to left*, or *Little - Endian* - the address of a 32-bit word matches the address of its least significant byte (Examples of CPU architectures are Intel x86, Pentium)
- *From left to right*, or *Big - Endian* - the address of a 32-bit word matches the address of its high-order byte (Motorola).

  Some systems support two modes at the same time. 

3. In some computers, data can be located in memory at any address; in others, alignment conditions are imposed on certain types.

4. A typical data type to store pointers to some object/data is a pointer. To store (or serialize the value of pointer) in some integer variable, you can use ```uintptr_t```. The ```uintptr_t``` integer type was introduced in C99. The ```uintptr_t``` is sufficient to store a pointer to any data, but formally not to a function.

5. A special value in C/C++ called a null pointer equal to a null pointer constant. A null pointer can be converted to any other type of pointer.

5. A null pointer in C/C++ is an integer expression that yields zero. Or such an expression cast into a pointer. The expressions below will not result in a compilation error, as much as we would like to:
```cpp
      void y(int*){}
      y(0);
```
6. In C++11, instead of NULL, you can use `nullptr`. That keyword stands for null pointer variable with type `std::nullptr_t.`

7. When using `union` for a mixture of structures that start the same way, there is a guarantee in C/C++ of an identical physical mapping of components "from this beginning".

8. In C and in C++ the components of the variable of structure type ```struct``` has addressed. There are the following guarantees:
* The component addresses are in ascending order. 
* The address of the first component is the same as the address of the beginning of the structure. And it is regardless of what endian the computer has where the program will run.

9. Structs are not allowed to perform comparisons with `==` or with `>`. The fundamental nature of this restriction in C/C++ is because, for objects, there may be holes in their memory layout that are filled randomly.

10. In C++, for the definition (not just declaration) of a variable in global scope you can use `extern int a = 0;`. But in fact `extern` is ignored.
It's due to (7.11.6, C++2003):
```
"A name declared in a namespace scope without a storage-class-specifier has external linkage unless it has internal linkage because of a previous declaration and provided it is not declared const. Objects declared const and not explicitly declared extern have internal linkage."
```
It also follows from this paragraph that declarations of non-const variables declared on namespace level have ```extern``` linkage by default in C++.

12. A compile-time string literal in C/C++ is statically allocated so that it is safe to return one from a function.


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

# Prefixes for strings from C++11

C++11 you can use the following prefixes for strings:

| # | **Suffix** | **Desciption** |
|---|------------|----------------|
| 1 | u'a'       | ucs2 symbol. Pretty like UTF-16, but surrogate pairs are not supported in UCS-2.      |
| 2 | U'a'       | ucs4 (UTF-32) symbol. |
| 3 | u"a"       | UTF-16 string. With support for surrogate pairs.                      |
| 4 |  U"a" | ucs4 (UTF-32) string                    |
| 5 | u8 "UTF8 string"      | UTF-8 string            |
| 6 | R"(asd\n)"  | Raw string. Analogue of Python's r"""str str""". Multiline is supported for such lines.        |

# Built-in type conversion

Before going into technical details about type conversion, let me be honest - it's hard to remember them, so possibly it is better to observe the big picture first:
```
The general requirement when converting integer types is the mathematical equivalence of the source and target values.
```

Now let's go into subtle technical details.

## Prohibited conversions

1. Converting a pointer to a function, a pointer to a data, and the other side direction is not allowed in C/C++.
2. Built-in conversion to a ```struct```, or to the ```union``` is not allowed.
3. C++ treats ```enum``` as distinct from each other and from integer type as well.
4. In C implicit conversion from integer to enumerated types is also allowed because in C, `enum` are C, but in C++, it is prohibited.
4. In C and C ++ implicit conversion from enumerated types to integer types is allowed.
6. Converting a pointer to a function to a pointer to data and the other side is not allowed in C++.


## The sequence of type conversions rules in C/C++
1. Trivial transformation. Conversion to identical types. A conversion from "function ..." to "function pointer ...."
2. If an overflow occurs during conversion to a signed type, then the value is considered overflowed and technically **undefined**.
3. If an overflow occurs during conversion to an unsigned type, the final value equals the "unique value" mod $2^n$ of the result. When using two's complement presentation, converting to/from signed to unsigned integers of the same size does not require any bit change.
4. If the final type is shorter than the original and both types are unsigned, the conversion can be performed by discarding the appropriate number of most significant bits. The rule is also applicable to integer types in 2-s complement notation.
5. When converting from float values to int, the final value should be equal to the initial value if possible. The nonzero fractional part is discarded. 
(The result is **undefined** if the value cannot even be approximated)

6. In C, conversion to floating-point types is possible only from arithmetic types. During converting from double to float, the final value must equal one of the two values closest to the original value. 
(The choice of rounding is implementation-dependent)

7. If it is impossible to convert from double or int to float then the value is **undefined**.
(Example: If the range of the target double type does not match)

8. Conversion from the type array of type T to a pointer to type T is performed by substituting the pointer for the first element of the array.

9. A value of any type can be converted to ```void```.

10. Conversion to ```void *``` and back guarantee the restoration of the original pointer value

11. In C, ```void *``` can be **implicitly** converted to a pointer to any type. In C++, **an explicit cast** is required. (Appendix C, 4.10, C ++ 2003 standard)

12. On the operands of unary operations, ordinary unary conversions are performed. The goal is to reduce the number of arithmetic types.
   * An array of type T $\to$ pointer to the first element (not applied for arguments of ```operator &``` and ```sizeof``` operators).
   * Function $\to$ function pointer
   * Conversions from an integer type of rank below int $\to$ to int
   * Conversions from unsigned integer types lower than int, int represent all values $\to$ values are cast ​​to integers
   * Conversions from unsigned integer types lower than int, but int does not represent all $\to$ values are cast ​​to unsigned int
13. On the operands of a binary operation, the usual unary conversions are performed separately for each argument, and after that, the regular binary conversions are applied.
14. If some operands of the binary operator have the type `long`, `double`, `double`, `float`, and the second operand has a rank lower, then it is cast to the type with the highest rank.
15. If both operands are unsigned, then both are cast to a higher rank unsigned type.
16. If both operands are signed, then both are cast in the signed type of the higher rank.
17. Unsigned operand and lower-ranked signed operand $\to$ unsigned type.
18. Unsigned operand and signed type operand of higher rank $\to$ signed type.
19. If the prototype is controlled by an ellipsis `...`, i.e., the function obtains varying argument number, then the usual unary conversions are performed on the operands. Also, besides that, `float` is always promoted to `double`. The float is not converting into a double if there is no ellipsis and the call is fully prototype-driven.

# Namespaces

The namespace is a mechanism for reflecting logical grouping. If some declarations can be combined according to some criteria, they can be placed in the same namespace to reflect this fact. 

**Namespace advantages:**
* Logical structure reflection
* Avoidance of name conflicts
* Express a coherent set of tools 
* Prevent users from accessing unnecessary tools 
* Do not require significant additional effort when using

**Namespace disadvantages:**
* Waste of time analyzing the assignment of objects to different namespaces
* Various additional nuances: 
  - A local variable or a variable declared via `using` hides external variables in relation to the block of visibility.
  - When libraries that declare many names are made available through the `using` directive, it is important to understand that unused name conflicts are not considered errors.
  - Elements of the same namespace can be in different files.

# New operator (memory allocation)

In C++, before the introduction of the exception mechanism, the `new` operator returned 0 when the memory allocation failed. 
In the C++ standard, `new` by default throws a `std::bad_alloc` exception. As a rule, striving for similarity to the standard is best. Better to modify the program to catch `bad_alloc` rather than check the return for 0. In both cases, doing anything other than throwing an error message is not easy on most systems. See paragraph 5.3.4. Subparagraph 13.
http://www.ishiboo.com/~nirva/c++/C++STANDARD-ISOIEC14882-1998.pdf

For Visual Studio compiler: 
1. `new(std::nothrow)` - does not throw an exception 
2. regular `new` - throws an exception. You can customize the behavior using linker options: http://msdn.microsoft.com/en-us/library/kftdy56f.aspx


# Exceptions

When a program is constructed from separate modules, and especially when these modules are in independently different libraries, it is convenient to divide error handling into two parts:
* Generation of information about the occurrence of an error situation that cannot be resolved locally.
* Handling Errors Found Elsewhere

*Error handling code can be shorter and more elegant using a return value, but this solution does not scale well.*

Generally, separating error handling code from "normal" code is a good strategy. Throwing an exception may leave the object in an invalid state.

Throwing an exception can be a source of memory and other resource leaks. It's best to rely on the properties of constructors and destructors and their interactions with exception handling to deal 
appropriately with an object. (Escape from a block by throwing an exception cleans up all created local automatic things in reverse order of creation.). Writing correct exception-safe code using explicit tries can be a difficult task.


## Extra Notes about use exceptions

* You can group exceptions by inheritance relation.
* Exceptions at the time of generation are copied. The const modifier in the catch block does not affect anything. However, the presence of a `T&` or `T` type signature is affected. The latter causes the copy constructor to execute. For `throw T();` you can't see the copy constructor run in VS 2012. But can be seen for:
```cpp
{T e; throw e;}
```
* Exiting a destructor by throwing an exception is against the requirements of the standard library.
* The process of calling destructors for automatic objects constructed on the path from a try block to a throw expression is called "stack unwinding."
* If a destructor called during stack unwinding exits with an exception, terminate is called (C++2003, 15.5.1). So destructors should generally catch exceptions and not let them propagate out of the destructor.
* If an exception is thrown but not caught, `std::terminate` is called. You can set your behavior with `std::set_terminate`.
* It is possible to rethrow an exception with `throw;`.
* When an exception is thrown in a constructor, the object's destructor is not called.
* If an exception is thrown in the destructor during the call to the destructor during exception handling, then this is considered an error in the exception handling mechanism, and `std::terminate()` is called. 
To distinguish the behavior of executing destructor due to normal call of the destructor, or during stack unwinding, you can use: `uncaught_exception()` in the destructor.

* The basic errors classes are `exception`, `logic_error`, `runtime_error`. Some others class: `bad_alloc`, `bad_cast`, `bad_typeid`, `bad_exception`, `out_of_range`, `invalid_argument`, `overflow_error`, `ios_base::failure`.

* If a function tries to throw an exception it didn't declare, it will result in a call to `std::unexpected`, which by default pulls std::terminate (p.429, Stroustrup, special edition)

```cpp
intf(); /* Can throw any exception */
int f() throw(); /* Throw no exceptions */
int f() throw(x2, x3); /* Throws only exceptions x2, x3 */
```

Starting from C++11 it's possible to use an empty exception specification `throw()` defined in alternative way via  `noexcept`.

```cpp
void g1(int) throw() {}
void g2(int) noexcept {}
```

Construction of interception of exceptions from the initialization list. Example:
```cpp
#include <stdio.h>

class C 
{ 
public:
  C() try : a()
  { puts("C()");  }
        catch(...)
  { puts("WOW!"); }
  int a;
};

int main()
{
  C c;
  return 0;
}
```


# Overloading

## Functions and operator overloading precedence

1. Exact type matching, or the matching achieved by trivial conversion (array name to a pointer, function name to function pointer, type `T` to `const T`).
2. Correspondence is achieved by promotion of integral types and promotion of real numbers to integers. (`char` to `int`, `float` to `double`).
3. Correspondence achieved by standard conversions (`int` to `double`, `double` to `int`), pointers to derivatives to pointers to base classes. Pointers to arbitrary types to pointers to `void*`.
4. Correspondence achieved with user-defined transformations
5. Correspondence due to ellipsis `...` in the function definition.

If a match can be achieved in **two ways** at the same criteria level, the challenge is considered ambiguous and is rejected.

Also overload function with Xvalue Reference `A&&` has priority under constant reference `const A&`.

Very popular fix the standard behavior of the compiler, not trying to find an overloaded function in B:
```cpp
class B  {
public:
	void f(int i) { cout << "f(int)\n"; }
};

class D : public B {
public:
    // fix "strange" behaviour
    using B::f;
    void f(double d) { cout << "f(double)\n"; }
};
```

## Template function overloading
Template function overloading searches for a set of suitable specializations according to steps (1-4) described below:

1. All specializations that can potentially be called.
2. If any specialization is the more specialized of the two, the less specialized is discarded.
3. Overloading allowed for functions from steps 1-2 and regular functions
4. If a regular function and a template function match equally well, the regular function takes precedence.

The call is considered an error if the function passed 1-4 is not found.

## Resolving the overloaded binary operator for x(op)y.

1. If X(type of x) is a class. Find out if the operator is defined as a member of class X or a base class of X
2. View operator declaration in the context of x(op)y expression
3. If X is declared in namespace N, look for operator declaration in namespace N
4. If Y(type of y) is declared in namespace M, look for operator declaration in namespace M

## Operators overloading rules in C++

Please check details in Standard. C++ 2003. p. 233. 13.5.1 - 13.5.7. 

According to the standard, operators cannot be overloaded as static methods of a class. It is possible to overload them:
* as functions 
* as non-static class methods. (The operators `=`, `[]`, `->` can be overloaded only in this way).

Next, you cannot overload the following operators: `.`, `::`, `.*`, `->*`, `sizeof`, `typeid`, `?:`.


# Namespace lookup rules
A namespace is a named scope. A namespace, unlike a class definition, is open to new features being added to it. The `using` directive applies more to namespaces than to classes.

1. If the function is not found in the context of its use, then an attempt is made to search in the namespace of the arguments. This rule does not pollute the namespace.
```cpp
namespace NameSpace {
  structType{};
  void func(Type x)
  {}
}
...
func(NameSpace::Type());
```
This mechanism is called an Argument-dependent lookup (ADL). It's very useful, for example, when calling some overridden operator on your type in a situation where you decide to define an operator in the namespace your type is in.

Some nuances I've come across: [https://stackoverflow.com/questions/45713667/unqualified-lookup-in-c](https://stackoverflow.com/questions/45713667/unqualified-lookup-in-c)
Various nuances of working with namespaces are covered in the appendix [1] B.10, page 924

2. A locally declared name and a name declared with a `using` directive hides a non-local declaration.

3. Local name declaration takes precedence over NS name, but the global declaration does not take precedence over variables imported from NS::*

4. Collisions of unused names are not treated as errors

5. Global names are in the "global namespace". It's just global. It differs from all namespaces (including the unnamed one). 
The global namespace differs from those defined through namespace only in that it is not necessary to write its name. 
In fact, It's only really worth thinking about it when you need to use ::global_var when you have a problem (3). The operator `::` stands for scope extension. 
With this construction, you will always look first in the global namespace first and then in the namespaces imported into the global namespace.

6. If the name is declared in the enclosing scope or in the current scope, then the name can be used without problems, without a full qualifier.
7. Continuous repetition of a qualifier distracts attention. Verbosity can be eliminated using the declaration:
7.1 Creating a synonym for a variable through `using NS::x;` It's called **using declaration**.
7.2 Creation of synonyms for all variables from namespace - through `using namespace NS;`. It's called **using directive**.

8. Placing 7.2 inside another NS opens up the way to combine/mix features from different namespaces.

9. Creating an unnamed namespace implies auto-generation of its name by the compiler and insertion `using namespace GEN_NAME;` to the source file with that unnamed namespace.

10. Names explicitly declared in a namespace and also made available with using declarations i.e. via `using NS::x;` take precedence over names made available via using directives i.e. `using namespace NS;`

11. Namespaces can be nested. To create an alias, you can use a construct like the following:
```cpp
namespaceAA = NameSpace::NameSpace2;
```
12. Namespace Search Rules in case of using nested namespace

Example with a variable "i" in ANSI ISO IEC 14882, C++2003, 3.4.1, (6) (page 30).
```cpp
namespace A {
  namespace N {
    void f();
  }
}
void A::N::f() {
    i = 5;
}
```
The following scopes are searched for a declaration of i:
1) innermost block scope of A::N::f, before the use of i
2) scope of namespace N
3) scope of namespace A
4) global scope, before the definition of A::N::f

Some relative things are here: https://en.cppreference.com/w/cpp/language/unqualified_lookup

13. One subtle addition to function names. 
Function names obtained from ADL are looked up in the namespaces of their arguments in addition to the scopes and namespaces considered by the usual unqualified name lookup.

# ```typename``` keyword
The typename keyword must be used in three tasks.

1. Replacing the keyword class with the word typename in the argument type declaration for a template class/function/method.

```cpp
template <typename> struct S{}
```

2. Accessing type names through the scope of the class that is the template argument.
```cpp
template <class T> struct S {
  typename T::SomeType a;
}
```
Comment by B. Stroustrup *"In some cases a smart compiler could guess, but in general it's not possible"*.

3. The typename keyword is required if the type name depends on the selected template parameter.
```cpp
template <class T> T findMax(const std::vector<T>& vec){
  typename std::vector<T>::const_iterator max_i = vec.begin();
  for (typename std::vector<T>::const_iterator i = 
  vec.begin() + 1; 
  i != vec.end(); 
  ++i)
  {
    if (*i > *max_i)
      max_i = i;
  }
  return *max_i;
}
```
There is also a very detailed description here about the `typename` keyword here:
[http://stackoverflow.com/questions/610245/where-and-why-do-i-have-to-put-the-template-and-typename-keywords](http://stackoverflow.com/questions/610245/where-and-why-do-i-have-to-put-the-template-and-typename-keywords).

# Class constructor and destructors

## Logic behind execute constructors
The order of working out the initialization of a class object in C++ is described in C++ Standard - ANSI ISO IEC 14882 2003; 12.6.2, p.230.

The order of initialization of classes and execution of constructors:

1. Depth first, left to right constructors of virtually inherited classes whenever they are located in inheritance tree.

```cpp
#include <stdio.h>

class A {
public: A(){printf("A()\n");}
};

class B:virtual public A {
public: B(){printf("B()\n");}
};

class C: /*virtual*/ virtual public A {
public: C(){printf("C()\n");}
};

class Branch {
public: Branch(){printf("Branch()\n");}
};

class D : public Branch, virtual public B, virtual public C {
public: D(){printf("D()\n");}
};

int main()
{
    D d;
    return 0;
}
```

Surprisingly, it will not be Branch() that will be printed first, but the output will be like this:
```
A()
B()
C()
Branch()
D()
```

2. Execution of constructors of directly base classes in the order from left to right from the class description (and not in the order specified in the initialization list).

3. Initialization of class members in the order specified in the class description (again, not in the order specified in the initialization list)

4. Execution of the function body of the constructor

## Logic behind execute destructors

When processing the destructor, identical actions behind logic of constructors execution is performed, but in reverse order.

4. Working out the body of the destructor for class members
2. Destructor of direct non-virtual base classes
1. If the object is the object of the "deepest" class in the inheritance graph, then virtual base destructors are called

# Deleting object of incomplete type

Deleting an object with an incomplete type. 
```cpp
class My;
My* ptr;
delete ptr; // undefined behaviour for incomplete types
```
For POD, and for an object without a destructor, something like C runtime free will be done, which does not need to know about the size of the object. 
In this case you're lucky, and you can typically delete dynamically allocated object, but in general it results in undefined behavior. (5.3.5 Delete C++2003).

# Return Value Optimization
Compilers may or may not perform optimization on return object from the function.

# Include search order
The original C specification says that the original directory in which the compiled file is located is used to look for a user-defined include file.
The reality is that it is necessary to clarify the rules according to the specification of the tool chain used. Or understand the essence of the experiments.

# Include naming

1. A standard header file whose name begins with the letter ```c``` is equivalent to a standard header file in the C library. (B. Stroustrup, Spec. Edition, p. 487, 16.1.2)
2. For each "C" standard library ```"X.h"``` header file, there is a corresponding C++ standard header file ```<cX>``` in C++.
3. But "X.h" defines function names in the `std` namespace, and also **imports those names into the global namespace**.
4. And "cX" defines function names only in the `std` namespace. ([1], 9.2.2, page 247).

# C++ variable initialization
1. There are a lot of types of initialization in C ++

```cpp
const int v1(expr);   // direct initialization
intv2 = expr;         // copy initialization
int arr[] = {1,2,3};  // bracket initialization
```

2. Static variables are initialized to zero for the corresponding type. Array and structure variables are initialized to zero if the initialization list is empty.

3. A reference in C++ shall be initialized to refer to a valid object or function. In particular, a null reference cannot exist in a well-defined program.

4. Types of initialization in C ++
* zero_initialization
* default_initialization
* value_initialization

More about initialization: 8.5, 8.5.1 Initializers from C++2003-10-15.

5. If for an array or structure the number of initialization values is less than the dimension of the array or structure, the rest of the elements are initialized with the default value for the corresponding type (as in the case of initialization of static variables).

6. In C++98/03 a `union` cannot have as a member an object with a user-defined constructor.

# std::initializer_list<T>
In C++98 constant member arrays and heap arrays are impossible to init, but in C++11 there is an idea to bring bracket initialization to everything.
```cpp
int a[] {1,8,8}
```
Here {1,8,8} - is an initialization list. This construction implicitly casting to `std::initializer_list<T>`. Ctor with initialization list argument has priority during overloading. 

Type deduction in template functions does not work for `std::initializer_list` type. But for auto works fine.  **It is one place where auto != template**. Example
```cpp
// gcc -x c++ -std=c++11 t.cpp
#include <stdio.h>
#include <initializer_list>
 
template <class T> 
void f1(T a) {}

void f2(std::initializer_list<int> a) {}
int main()
{
//  f1({1,2,3}); // DOES NOT COMPILE
  f2({1,2,3});
  auto f3 = {1,2,3};
  return 0;
}
```

7. In [1], 10.4.6.2 for C++2003: *"You can initialize a class member that is a static constant of an integral
type. If and only if you do so, then you need to declare this member once somewhere."*.

# Generate or Suppress generation of special class members

You can explicitly force the compiler to generate default code for a method for which this behavior can take place through `=default`. You can disable the use of (any) function/method by specifying `=delete`.

# Lambda functions

*Closure* in math set with its boundary (*functional analysis*) or family function which can be achieved via constructing all possible formula under basis function (*discrete math*).

But in C++ closure is object (instance of the class) with:

  `ret_type operator()(<list of arguments>) const`

That object is created by compiler during parsing lambda expression. So Lambda's in fact generate C++ classes with operator(). You can refer to variables with static storage duration in lambdas. They all are captured.

You can use lambda to capture values "by value". In such a case captured vars will be copied to a function object (closure).

Example: `[captureVar1,captureVar2](int arg1){}`

You can capture variables by reference. `&` - in context of lambda `&` means capture by reference, not dereferencing operator. Example: `[&captureVar1,&captureVar2](int arg1){}`

It exists notation to capture all non-static vars by value, or by reference:

`[=](int arg1){} // capture all not-static vars by value`

`[&](int arg1){} // capture all not-static vars by reference`

Next it exists notation to capture all non-static vars by value, or by reference and specify something for another variables. Example of capture all not-static vars by reference, but by value capture Param2:

`[&,Param2](int arg1){}`


Lambda return type can be deduced if lambda is one expression in C++11. Or you can explicitly specify it.

`[=](int arg1)->trailing_return_type{return trailing_return_type();}`

If lambda has more than one expression, then the return type must be specified via the trailing return type in C++11, and it will be deduced in C++14. Similar trailing syntax can be applied to auto functions and member - functions.

You can capture only local vars, not member variables of the object. Also, you can allow lambda to modify captured values

```cpp
        int x = 12;
        auto a = [=]() mutable  ->void  { x = 1; };
```

You can capture this pointer explicitly
```cpp
auto a = [this]() ->void  { aa = 1; };
```
or implicitly, because default capture also makes this available.
```
auto a = [=]() ->void  { aa = 1; };
```

Even lambda is not a function pointer, and it is not an anonymous function, but **capture-less** lambdas can be implicitly converted to a function pointer.

In C++14 the extra feature which has a name is **"init capture"**. It allows performing arbitrarily declaration of closure data members:

```cpp
auto interpolate =
[min = toFloat(0), max = toFloat(255)](int value)->float { return (value - min) / (max - min);};
```

Starting from C++14 you may want not to specify types of arguments. It's called generic lambdas. Example:

```cpp
auto test = [](const auto& x){std::cout << x;};
```

Starting from C++20 the same auto syntax can be applied for generic functions. Both of that things is just a shorthand for template methods.

Starting from C++20 it's possible to be more explicit about the type and define what is called **Lambda Templates**. Example:

```cpp
auto multiply = []<class T>(T a, T b) {return a*b;};
```

# Smart Typedefs

Startinf from C++11 there are "Alias Templates". Using declarations can now be used for "partially bound" templates:

```cpp
template <class T>
using MyAllocVec = std::vector<T, MyAllocator>; 
// MyAllocVec is alias template
```

They cannot be partially specialized, and can be used wherever `typedef` is used.

# Move semantics
Move brings objects in a valid, but in unspecified state. Objects in fact can be reused after movement.

Move semantics is one of the main innovations of C++11. Move is useful for objects that store part of their state in a heap. 

Moving is never slower than copying and usually faster. For some objects, there are only move semantics for example thread.

It doesn't make sense to implement move if (1) its speed is worse or the same as copying, (2) This operation is not on the critical execution path in the program. You shouldn't use `std::swap` to implement move. It doesn't make any sense.

In C++98/03:
  LValue - something from which you can take the address. (variables, or lvalue reference)
  RValue - something from which you can not take the address (in 99% of cases these are unnamed temporary variables)
  A good counterexample is something that is an rvalue but has a name - `this`.
    LValue reference - regular references
    Lvalue may bind to LValue reference
    Rvalue may bind to LValue const reference

In C++11:
RValue reference - T&& (C++11). They behave like an LValue reference. The goal is to have a moving candidate.

Rvalue may bind to a non-const rvalue reference. Lvalue may not bind to an rvalue reference.

**Important rule: move from lvalues ​​is never executed, it is copied.** The construction `void f(T&&)` takes precedence over `void f(T&)` if both can be called.

C++11 considers `noexcept` - calling any destructor, memory allocation. Move self to self - usually not checked, because this is not normal behavior.

## The first scary thing
The move constructor should be written carefully, the fact is `T&&`, although there is an rvalue reference,
but in the context of the body that `T&& x` sees, x is already an lvalue. The most confusing thing about C++11.

Therefore, for example, in the initialization list in ctor, you need to write `Base(std::move(rhs))`.
`std::move` - turns expression into rvalue. `std::move` could be called rvalue_cast

## The second scary thing
There is a special construction `T&& Param` Definition in Template the rule is valid only for constructions of the form
```cpp
template <class T>
void f(T&& arg)
{}
```
That construction is processed by special rules:
arg is Lvalue => deduced to `void f<T&> (T& arg)`
arg is Rvalue => deduced to `void f<T> (T&& arg)`

Universal reference(Term by Skott Mayers), binds everything:
```cpp
template <class T>
void f(T&& arg)
{}
```

* std::move - unconditional reference value cast.
* std::forward - conditional cast for universal references (universal references -- no official term, coined by Scott Myers)

## Reference Collapsing Rules
In C++ you can not delcare a reference to reference, but when reference collapsing occurs during template types substitution there are the following rules:

`T&&` => `T&` - valid from C++03

`T&, &&` => `T&` - valid from C++11

`T&&, &` => `T&` - valid from C++11


`T&& T&&` => `T&&` - valid from C++11


# Variadic templates
In our opinion that topic is pretty difficult.

The motivation is to have ability to work with varying number of template parameters. The smallest example:
```cpp
template <class T...>
void f(const T&...arg)
```

Example of performing printf in variadic template style:
```cpp
template<typename T, typename... Args>
void printf(const char *s, T value, Args... args)
{
    while (*s)
    {
        if (*s == '%')
        {
            if (*(s + 1) != '%')
            {
                std::cout << value;
                s += 2;
                printf(s, args...);
                return;
            }

            ++s;
        }

        std::cout << *s++;
    }    
}
```

**First thing:** In variadic template for ellipses `...` you can put spaces anywhere around it. And `...` are used in fact for various purpose.

**Second thing:** the only way to get the next template argument is to recursively call a function whose template parameters are specified as ```<TExtractType, RestTypes...>```. So if you have ever seen functional programming languages, that construction looks pretty close to that.

* `class ...Args` - parameters pack in template parameters list with optional name.
* `(Arg&&....params)` - function arguments parameters pack.
* `Args...` - unpack parameters. Used inside the body of th function.
* `sizeof...(Args)` - sizeof of parameters in terms of number of elements in Args. (It'not the size in bytes).

Variadic templates has been introduced in C++11, the last trick with variadic template is called *fold expression* has been introduced in C++17. Unary syntax for fold expression:
```cpp
template<typename... Args>
bool allLeftFold(Args... args) { return (... && args); }

template<typename... Args>
bool allRightFold(Args... args) { return (args&& ...); }

```

# Virtual and Polymorphism in C++
To get runtime polymorphic behavior the member functions must be `virtual` and objects must be manipulated through pointers or references. When you're calling a function using the scope resolution `operator::` that ensures that the virtual mechanism which is builtin in the language **is not using**.

When manipulating an object directly (rather than through a pointer or references) and its exact type is known by the compiler then in that case, run-time polymorphism is not needed and the call will be done without using vptr's.

A virtual function invoked from a constructor or a destructor reflects that the object is partially constructed.


# Override (from C++11)
The use of override is optional, but being explicit allows the compiler to catch mistakes, such as misspellings of function names or slight differences between the type of virtual function.

So it can be a situation when the function is intended to override something, but due to mistake, it is a new virtual function. But in the case of using `override` will remove this problem. Better to not repeat virtual in a derived class, but if you want to be explicit use `override`. Also `final` provides prevent further overriding. B. Stroustroup said:

*"That it’s illogical that virtual is a prefix and override is a suffix.  This is part of the price we pay for compatibility and stability over the decades".*

Curiously, override is not a keyword; it is what is called a contextual keyword.  E.g. It can be used as an identifier."

```cpp
struct Base
{
    Base(){puts("Base()");}
    Base(const Base&){puts("Base(const Base&)");}	
    virtual void f(){} // declare functions in a base class that can be redefined in each derived class
    virtual void g(){} // declare functions in a base class that can be redefined in each derived class
};
 
struct A: Base
{
    A(){puts(__func__);}
    A(const A&a): Base(a) {puts("A(const A&)");}
    virtual void f(){} // By default, a function that overrides a virtual function itself becomes virtual
    void g(){}         // By default, a function that overrides a virtual function itself becomes virtual
};
 
struct B: Base
{
    B(){puts(__func__);};
    B(const B& b) : Base(b) {puts("B(const B&)");}
   // Better to not repeat virtual in a derived class, but if you want be explicit use "override"
   // final provides prevent further overriding
   void f() override final {}	
   int override = 7;
};
```

# Some class operators (since C++11)
```cpp
class X { 
public:
  // "ordinary constructor": create an object
  X(Sometype);            
  // Default constructor
  X();                    
  // Copy constructor     
  X(const X&);            
  // Move constructor  
  X(X&&);                 
  // Copy assignment: clean up target and copy     
  X& operator=(const X&); 
  // Move assignment: clean up target and move     
  X& operator=(X&&);      
  // Destructor: clean up
  ~X();                   
};
```

# Various constants flavors.

## constexpr


`constexpr` - indicating that it should be possible to evaluate the function at compile time if given constant expressions as arguments. The main idea due to B. Stroustroup is that it brings type-rich programming in compile-time.  The deep reason that includes this into language lies in that a lot of communities ask B. Stroustroup to include in languages something which will make table-lookup easier. And because it's near impossible to be faster than table lookup then this concept can make sense.

C++11 `constexpr` functions had to put everything in a single return statement. C++14 `constexpr` functions, not necessarily had to put everything in a single return statement. Example: 
`constexpr int sum(int a, int b) {    return a + b; }`

A `const` differs from a `constexpr`. 

`const` - can be initialized by something that is not a constant expression.

`constexpr`  - can be conceptually initialized only really by a const at compile time.
```cpp
constexpr int a = 12;
```

# Small features (from C++11)

Other features
1. `constexpr` - const during compile time.



2. `emplace_back` - construct object directly in place in memory of the container
3. `vector::shrink_to_fit` method
4. `noexcept` specification - like throw() specification for functions from C++98, but it allows more optimization
5. `static_assert` - assert during compile time
6. `alignas` operator from (C++11) enforce alignment. `alignas` allocates an object with the requirement to allocate it with alignment suitable for another type. Example:
```cpp
alignas(int) char buff[1024]; 
```

7. `alignof(x)` - alignment operators built into the language. Example:
```cpp
  std::cout << alignof('c');     // print alignment for char's
```

8. Default Member Initializers (C++11)

When a data member of a class is defined, we can supply a default initializer called a default member initializer. The default value is used whenever a constructor doesn't provide a value.  This simplifies code and helps us to avoid accidentally leaving a member uninitialized.
```cpp
class X {
  int i = 4;
  int j {5};
};
```

9. User-defined literals or UDLs (C++11)

Unsurprisingly, literals with user-defined suffixes are called user-defined literals or UDL.
```cpp
long double operator "" _w(long double);
int main() {
    1.2w; // calls operator "" _w(1.2L)
}
```

10. `[[noreturn]]` attribute. Placing [[noreturn]] at the start of a function declaration indicates that the function is not expected to return. Example:

```cpp
struct S { 
[[noreturn]] virtual inline auto f(const unsigned long int* arg)-> void const {}
};

[[noreturn]] void exit(int); 
```

11. Anonymous unions (C++11)
```cpp
  union {
     float f;
     uint32_t d;
  };
  f = 3.14f;
```
12. Type Alias.

13. Type Alias (C++11)
```cpp
// Usual namespace alias from C++98.
namespace AA = std;
// Usual typedef
typedef AA::vector<int> VecInt1;
// Alias for bind some types. From C++11
using VecInt2 = AA::vector<int>;  
```

14. Interestingly that `static` local variable in C++11 garantees thread safe initialization. It was not a case in C++03. So static variabes local variables are guranteed to be initialized only once,

# Small features (from C++14)

1. ```[[deprecated]] attribute (C++14)```
This indicates that the use of the name or entity declared with this attribute is allowed, but discouraged for some reason. Compilers typically issue warnings. For example:
```[[deprecated]] void func(int);```

2. Return Type Deduction
```cpp
auto f() {
   return 42;
}
```

3. Binary Literals
```cpp
unsigned char a = 0b00110011;
```

4. Variable templates. Example:
```cpp
template<class T>
inline constexpr T pi = T(3.14159)
```

# Small features (from C++17)

1. Structured Binding(C++17)
```cpp
struct Entry {  
   string name;   
   int value; 
};
auto [n,v] = read_entry(is)
```

The `auto [n,v]` declares two local variables n and v with their types deduced from read_entry() return type. This mechanism for giving local names to members of a class object is named as a structured binding.

2. Deduce template parameters from constructor arguments.
```cpp
// Example program
#include <iostream>
#include <string>
template <class T>
class A {
public:
    A(T arg)
    {
      (void)arg;
    }
};
```
Starting from C++17 it's possible to just write `A a(123);` instead of `A<int> a(123)`. Before C++17 such feature was supported only for template functions, but not for template classes.

3. Compile-Time If (C++17)

Only the selected branch is instantiated via using some compile-time expression. This solution offers optimal performance and locality of the optimization.

```cpp
// Example program
#include <iostream>
#include <string>
#include <type_traits>
template<typename T> void update(T& target) 
{
 if constexpr(std::is_pod<T>::value)         
    simple_and_fast(target); // for "plain old data"     
 else       
    slow_and_safe(target);   // ... 
}

int main() {
   return 0;
}
```


# Small features (from C++20)

1. `[[no_unique_address]]` attribute allows an empty non-static data members to share space with another subobject of different type.

2. Spaceship operator (From C++17)
```cpp
operator <=>(const Y&)
```
After definining what is called spacehsip operator compier generate based on that various 6 comparision operators automatically.

3. `[[likely]]` and `[[unlikely]]` attributes are applicable for `case` branches in switch statement to give a compilers a hint to optimize certain branches.

```cpp
switch(value) {
  case 1:
    break;
  [[likely]] case 2:
    break;
}
```

4. `std::format()` to replace sprintf and ostringstream. 

5. Compile time information about current source file `source_location::current()`. Defined in `<source_location>`.

6. Attribute `[[nodiscard(reason)]]` applied for function and describes consequence of discarding return object from the function call.


# Modules (from C++20)

Standart `#include` preprocessor derictive helps organize project, but at a huge cost. The desirability of modules due to B.Stroustroup is already well known in 1980.

Modules will come from C++20 to upgrade the understanding of header files. And there are reasons to include it in standards.B.Stroustroup mentions two things:
- Google reports x2-4 improvements in compile-time
- Microsoft reports x5-x50 times improvements in compile time

Modules result in reduced compilation times. The order in which you import modules never matters.


# The suffix syntax for function return type

It is not primarily about templates and type deduction, it is really about scope. One more example when it was useful (http://www.stroustrup.com/C++11FAQ.html)
```cpp
template<class T, class U>
auto mul(T x, U y) -> decltype(x*y) {
	return x*y;
}
```

We use the notation auto to mean "return type to be deduced or specified later."

# Predefined identifiers and macros

`__func__` - In C99, a predefined identifier with the name of the current function. C++11 officially support that too.

`__LINE__`, `__FILE__` - current line number, and current source file name

`__DATE__`, `__TIME__` - date and time of file translation

`__STDC__ ` - compiler conforms to the C standard

`__VA_ARGS__ ` - only C++ and C99 formally support that. Built-in name that can be used for macros with arbitarily number of argument. When the macro is invoked, all the tokens in its argument list `...`, including any commas, become the variable argument. C++11 officially support that too.

`__cplusplus` - C++ version

`__STDC_VERERSION__` - version of standart C.

```cpp
#include <stdio.h>
int main()
{
#ifdef __cplusplus
 printf("C++ version %li\n", __cplusplus);
#elif defined(__STDC__)
#if defined(__STDC_VERERSION__) &&__STDC_VERERSION__ > 199901L
 printf("C99 standart\n");
#elif defined(__STDC_VERERSION__) &&__STDC_VERERSION__ > 199409L
 printf("C89 with additions 1\n");
#else
 printf("C89\n");
#endif
#else
 printf("C not standartizied\n");
#endif

  return 0;
}
```

# Memory Types and pointers

1. An ordinary string literal has the type “array of n const char” and static storage duration.
2. About a pointer to constant data and a constant pointer [2], p. 105. In principle, a possible trick to remember this is to read the expression from right to left and to which "const" type or variable is closer to that and apply this modifier.
```cpp
int* const const_pointer;
const int* pointer_to_const;
```
3. Quite a lot of important information is contained in "C++2003 5.3.3 Sizeof" including the following:
* ```sizeof(char)``` with all variations of char is always one byte.
* ```sizeof(bool)``` and ```sizeof(wchar_t)``` is implementation-defined.

4. Also, ```sizeof``` of structures in C/C++ is equal to the amount of memory to store all components, space for padding between components, space for padding after structures. 

5. The ```sizeof``` operator applied for array of structures and for other types, the following rule must be fulfilled: *The size of an array of N elements in bytes is equal to N times the size of the array element.*

6. In C/C++, a function pointer expression can be used to call a function without explicitly dereferencing the pointer, i.e. you can call the function as via using function pointer via `(*f)()` or via ```f()```

# Function nuances

1. There are two kinds of function call in C++ only: *ordinary function call* and *member function call*. A static member function (9.4) is an ordinary function. (С++ ISO/IEC 14882 2003-10-15)
2. In functions with `void` return types or when return type is absent e.g. in constructors/destructors you can have the absence of a ```return``` statement in a function body. It is equivalent to an explicit ```return;``` at the end of the function body.

3. But due to (C++2003, 6.6.3) *"Flowing off the end of a function is equivalent to a return with no value; **this results in undefined behavior in a value-returning function**."*
4. In C++, the ```main``` function cannot be called recursively.

# Requirements for C++ instructions

1. In C++98/03 you cannot modify a variable more than once without a sequence point in C++03/98. *Sequence point* - semicolon, function return, function jump, and some others, please check specification.

2. C++11 introduces the term *order of evaluation*. The term *sequence point* is no longer used.


# Exceptions to the one definition rule

You can read about that in details in [1], 9.2.3 p. 248

There can be more than one definition of the following things:
1. class type (Clause 9)
2. enumeration type (7.2)
3. inline function with external linkage (7.1.2)
4. class template (Clause 14)
5. non-static function template (14.5.6)
6. static data member of a class template (14.5.1.3)
7. member function of a class template (14.5.1.1)
8. template specialization for which some template parameters are not specified (14.7, 14.5.5)

That same definitions are acceptable when:
1. They are in different translation units
2. They are identical token by token
3. The meaning of token is the same in both translation units (Checking this is not included in the capabilities of the programming language itself, but is assigned to the toolkit)

All exceptions to the One Definition Rule is described in C++2003, p.23, §3.2/5.

# Technical Differences and portability between C and C++

1. Old C style function declarations are not allowed in C++
```cpp
double alt_style( a , real ) /* Obsolete function definition */
    double *real;
    int a;
{
    return (*real + a);
}
```

2. C programs should not use names that are keywords in C++ if one wants to be compatible with portability.

3. C++ style comments `//` only appeared in C99.

4. C++ has new operations ```.*, ->*, ::``` which are not in C

5. Different memory for char literal in C and in C++
```cpp
sizeof('a') == sizeof(char) // C++
sizoef('a') == sizeof(int)  // C
```

6. C++ 1998 uses the C89 preprocessor, although the C language has changed: Tradition C, C89, C95, C99, C11

7. Struct tags in C++ are included in the "other names" namespace.
In this space are
* variables
* functions
* typedef names
* enum constants

Therefore, ```struct n{}; typedef double n;``` correct in C but not in C++.

7. Although for C++ type tag names (struct, union, enum) are implicitly declared with using `typedef`, but still they can be hidden by variables in the same scope `S S;`.

8. C99 has pointer qualifier `restrict`, which is not in official specification of C++98/03/.

9. Support of ```varying array``` array. In C99, the last member of a structure can be a flexible array, and it is also possible in C++.

10. In C99, but not in C++, there is a ```flexible arrays```. That arrays with a size specified via a non-const variable. In C99, to pass such arguments to a function, use the notation `void g(int pp[*], int k){}`.

11. Different initialization of the char array. In C++, the array must be of sufficient size to hold the "\0" character
```cpp
char a[3]="12"; char aEquiv[]="12";  // ok in C/C++
char a[3]="123";                     // ok in C, but not in C++
```
11. C99 has named initializers for structures and positional initializers for arrays, C++03 does not.

12. The definition of ```struct``` and ```union``` in C++ have block scope.

13. ```const``` declarations are ```static``` by default in C++, but ```extern``` in C (Appendix C. C++2003)
7.11.6, C++2003:
*"A name declared in a namespace scope without a storage-class-specifier has external linkage unless it has internal linkage because of a previous declaration and provided it is not declared const. Objects declared const and not explicitly declared extern have internal linkage."* It also follows from this paragraph that declarations of non-const variables declared on namespace level have extern linkage by default in C++.

14. C++ declaration ```void f()``` is equivalent to void ```f(void)``` in C. The declaration in C ```void f()``` state that function has an indefinite number of arguments.

15. If the array is multidimensional, then in all cases only the leftmost index can be omitted, in order to be able to determine the size of the array. Also in C99 component-wise initialization is allowed, and that is nor allowed in C++98/03.

16. In C, but not in C++, you can write, although this is strange: ```sizeof(struct S{int a;});```

17. Implicit cast from integer type to enum is allowed in C but not in C++. C++ 2003-10-15. page 113. 7.2.5: *"The type of an enum is an integer type that must support all underlying values. In C, enum has a synonym for int."*

18. In C++, converting a void pointer to any reference type requires an explicit cast operation. And in C, this is done implicitly.

19. Unconditional branching through ```goto``` is allowed in the middle of a nested block in C (while initialization of automatic variables is not guaranteed), this is not allowed in C++ in general, but there is an exception. The exception is for POD types - you may skip their intitialization. However, there are no guarantees for initialization of them.

20. In C++, there are more stringent requirements for inline functions - an ```inline``` function must be declared as such in all source files, in C99 this is not the case.

21. In C++, an ```inline``` function, in terms of code, can have an address and static variables inside, in C it is not allowed.

22. In C99, the compiler must see the function definition, i.e. the function should be defined so that it is inlined in ```*.h```. The compiler can choose to actually what to do:
* inline calls
* not inline
* partially inline.

23. C++ allows declaration in conditions, and it's not allowed in C.

24. There is no such type as a reference in C. (References are described in "С++2003, 8.3.2. References").

25. There are no overloaded functions in C.

26. C++ has default parameters, and they are not allowed in C.

27. In C++ there is a namespace mechanism with namespace, and it does not exist in C.

28. In C you can use ```exit()``` and ```abort()``` with no problems, but in C++ the destructors of local objects are not called.

29. Overloading of operators, functions is allowed only in C++.

30. C does not support General-Purpose-Programming with templates.

31. C99 has a predefined identifier ```__func__```. This identifier is implicitly defined by the compiler at the beginning of the function body as static const char ```__func__[] = "function-name"```. Such identifier was absent in C++98/03.

32. In C++ operators that are not presented in C language usually have the highest precedence, except for ```throw``` which is only above the comma operator ```,```.

33. In C, there must be at least one element in the initialization list when a structure or array is initialized. 

34. Prior to C99, i.e. in C89, C89 with extension there was a restriction on where automatic variables can be defined - only at the beginning of a local block. In C++98/03 already you can declare local variable anywhere.

# Templates
1. In addition to type, template parameters also include Non Type Parameters, which can have the type of integral constant, reference, and a pointer to a given or function. Pointers to data of function must have an external link type.
2. You can use `template` to create a specialization for array with a fixed size.
```cpp
#include "stdio.h"

template<class T>
void p(T a){ puts("not array"); }
//
template<class T>
void p(T a){ puts("not array"); }
//
template<class T, int sz>
void p( T (&t)[sz] ) { puts("array"); }
//
int main(int argc, char *argv[])
{
     intq[3];
     p(q);
     return 0;
}
```
3. Very rarely, but sometimes during using templates inside templates there is a need for the `template` qualifier is needed in case of difficulty in understanding.
```cpp
template <typename S, typename T>
T* allocate(S& storage, int numberOfElements)
{
     T*res = 0;
     // res = storage.alloc<T>(numberOfElements);
     res = storage.template alloc<T>(numberOfElements);
     return res ? true : false;
}
```
For more info: please view at "B.13.6 template" in Special Edition, Biern Stroustrup.

4. An empty `template<>` is syntactically reserved for explicit specialization, and cannot be used to create a template without parameters.

5. A template specialization can be complete (type int), partial (type that uses T as the basis for something else). However, the general template must be declared before any specialization, whether partial or complete. Also partial specialization only works for classes but doesn't work for functions. Example:
```cpp
template <class T>
struct Single
{
  Single() : var(T()) {}
  T var;
};

template <class T>
struct Single<T*>
{
  Single() : var(T()) {}
  T var;
  int extra_for_ptr;
};

template <>
struct Single<int>
{
  Single() : var(int()) {}
  int var;
  int extra_for_int;
};

int main()
{
  Single<int> a;
  a.extra_for_int = 1;
  Single<int*> b;
  b.extra_for_ptr = 1;
  
  return 0;
}
```

## Template syntax remarks
When instantiating a template, starting from C++11 not necessary to make a space in `>>`. In the case of specifying an integral type in a template parameter, and whish to perform right-shift `>>` you should enclose the expression in parentheses starting from C++11. 

Example of using `>>`:
```cpp
template <class T, int size>
class AA
{};
AA<std::vector<int>>, 2> obj;
```

Derivation of the template from the list of function arguments
from longer to shorter form A->B->C. On the complex rules of admissible derivation of template arguments functions see [1], 13.4.
```cpp
template <class T>
void swap(T* a, T* b)
{
   Ttemp = *a;
   *a = *b;
   *b=temp;
}
//A
template<>
void swap<float>(float* a, float* b)
{
   float temp_temp = *a;
   *a = *b;
   *b = temp_temp;
}
//B
template<>
void swap<>(double* a, double* b)
{
   double temp_temp = *a;
   *a = *b;
   *b = temp_temp;
}
//C
template<>
void swap(int* a, int* b)
{
   int temp_temp = *a;
   *a = *b;
   *b = temp_temp;
}

int main()
{
   int a = 0, b = 0;
   swap(&a, &b);
   return 0;
}
```

Default template arguments type must occur at the end for class or variable template. However, for function templates it's not a requirement, because for functions there is a rich type deduction template mechanism.

For compilation purposes you may want to request explicit template instantiation. Explicit instantion of a class template instantiates all members. It's possible to instantiate only individual template class member function too.

Example of syntax:
```cpp
template class MyVector<int>;
template void f<int>(int&);
template void g(double&);
template void MyVector<int>::size();
```

Also, one more complication - there must be exactly one definition of the corresponding specialization. So if you instantiate explicitly template in one translation unit, you should not explicitly instnatiate in another translation unit.
Example of syntax:
```cpp
extern template class MyVector<int>;
extern template void f<int>(int&);
extern template void g(double&);
extern template void MyVector<int>::size();
```

## Reference collapsing
The C++ standard allows reference collapsing in templates. Allowed to collapse `T&` into `T&`. Example:
```cpp
template <class T>
void f(T& val)
{
val = 0;
}

int i = 0;
f<int&>(i); // during compiletime f<int&>(int&&) => converts into => f<int&>(int&)
```

# Auto type deduction
The `auto` in C++98/03 was an explicit memory type for local objects, but starting from C++11 it's a type, automatically deduced similar to `template` arguments. The `auto` works in usual functions for variables and for arrays. For auto, the deduction is identical to the output for `template` function arguments.
```cpp
auto v1(expr); // direct initialization
auto v2=expr;  // copy initialization
int arr[] = {1,2,3};
for (auto x:arr) {
  printf("%i\n", x);
}

auto x1 = {1,2,3,4}; // x1 is an initializer_list<int>

// Bracket/Uniform initialization via using {} in form of list initialization does not allow narrowing
```

Auto can be used jointly with `constant` `volatile` type qualifiers (cv) and with reference and pointers. Examples:
```cpp
int ii= 1;
const auto * p_ii = &ii;
const auto& p_ref = ii;
```

# Range based for loop (since C++11)

Starting from C++11 there is a new syntax for `for` loop named as "range based for loop". Example:
```cpp
for (auto i : v) 
  std::cout << i;
```
Range-Based for Loops valid for any type supporting the notion of a range. One of the following constructions should be valid:
* **obj.begin()** and **obj.end()** 
* **begin(obj)** and **end(obj)**

# Inline function call
Working with inline functions is described here: https://isocpp.org/wiki/faq/inline-functions. How to work with inline functions
```cpp
// inline.cpp
// empty
// inline.h
#include <stdio.h>
void f();

inline void f()
{
     printf("F inline");
}
```
And
```cpp
// main.cpp
#include "inline.h"

int main()
{
     f();
     return 0;
}
```

# Basic integer types

In C and in C++98/03 there are three representations of signed integers of n bits that are allowed for implementation:

* two's complement (twos-complement-notation) [-2**(n-1), +2**(n-1)-1]. Positive numbers are represented in the usual way, the most significant bit of the sign is set to 0
negative numbers are obtained as (reverse bits(number)+1) in ASM instruction notation for x86 sounds like a NEG operation
1000000..000 is the maximum negative number that has no positive equivalent.

* one's complement (ones-complement-notation) [-2**(n-1)+1, +2**(n-1)-1]
Negative numbers are the complement of all bits of the corresponding positive number. In this representation, positive and negative zero are possible.

* signed integer representation (sign-magnitude-notation) [-2**(n-1)+1, +2**(n-1)-1]
The representation of the modulus of negative and positive numbers is identical. The sign of the number is stored in the most significant bit.

* Special dedicated type for enumerating integer constants from C89/99/11, C++98/03/11 is called `enum`. There are some subtleties with it:

* In C98/C99 then `enum` type is in fact synonym for integer with type `int`.
* Unlike C98/C99 the C++ language treats each enumerated type as specific type and from integers as well.

In reality that underlying type for C++ has some underlying integer type to actually store values, but it has not been specified. 

Starting from C++11 now we have two type of enums: **Strongly typed enums(or scoped enums)** and usual **enums**. Strongly typed enums does not support implicit conversion to int, support it's own namespace, it's possible to specify for them underlying type. The default underlying type for strongly typed enums is `int`. Example:
  ```cpp
  enum class Color : int{red,green,blue};
  ```

For ordinary enums in C ++ 11, as in C ++ 98, by default, nothing is said about the underlying type. You can make a forward declaration for enums if the underlying type is specified.

B.Stroustrup in his blog notes that it is now possible to explicitly (optionally) use the name of a regular and scoped enum as a namespace, to refer to its elements, as it were, through the namespace of a new type.

# Basic integer types nuances

1. The compiler's use `unsigned` or `signed` in the absence of an explicit type specification is not defined for `char`. 

2. The compiler's use `unsigned` or `signed` in the absence of an explicit type specification is not defined for bit fields.

3. In general, the result of doing a right shift for signed integer types in the case of negative numbers is undefined.
The compiler implementer can perform either a logical right shift or an arithmetic shift. ([2], p. 252)

# Language nuances
1. What does it mean ```A(*B)```? It can be declaring a variable or calling a function. This ambiguity makes the C grammar Context-Sensitive, and not LALR(1).

2. In C++ and C, the order in which subexpressions are evaluated is not defined ```A(F(), G())```. 

3. The compiler is allowed to evaluate the operands of a binary operation in an arbitrary order, as well as perform optimizations depending on the associativity and commutativity of the operation.

4. In C++, access control is later than ambiguity.
```cpp
class A {
public:
  int a;
private:
  int a;
};
A z;
z.a = 1; // Compilation error
```

5. The constructor also introduces an implicit conversion. To suppress this implicit constructor conversion
must be declared with the `explicit` parameter. ([1], p.333)

6. In C/C++ when using custom conversions via constructors without `explicit` keyword or defined `type conversions` - only one level of implicit conversions is allowed.

# Dynamic Memory Allocation

## Placement New

There are such variations of the new operator:

1. Usual placement `new`. Creation of an object, but using the already prepared address space. If the implementation needs to store some meta-information, then it can be the case that `b != address`. Example:

```cpp
#include <new>
int *b = new(address) int(init_value);
```

2. Overloaded operator new as a new global function. Example:
```cpp
void* operator new(size_t sz) {return a.allocate(sz);}
void operator delete(void* ptr)
```

3. Overloading `new` with custom parameters. The first argument to the operator is the size in bytes and calculated automatically via `sizeof`. After that there is a list of arguments that you decide clients should pass. Example:
```cpp
void* operator new(size_t sz, Arena& a, float b) 
{ return a.allocate(sz);}

new(arg2, arg3) SOMETYPE()
```

4. Operator overloading in a class. You can define new/delete within a class. It's good practice to make new/delete `static`.
However, even if static is not explicitly specified, the operator will be implicitly static.


## Pseudo Destructor
When you very need and when you understand what you're doing you can actually call in C++ destructor via using **pseudo-destructor**. Moreover the **pseudo-destructor** can be virtual. Of course you need to do that in very wrale cases.

```cpp
#include <stdio.h>
#include <utility>
class A {
public:
 A()           {printf("A()" "\n");}
 virtual ~A()        {printf("~A()" "\n");}
};
class B : public A {
public:
 B()           {printf("B()" "\n");}
 ~B()        {printf("~B()" "\n");}
};
int main()
{
 A* a= new B;
 a->~A();
}
```
# Language nuances

C/C++ postfix operators have higher priority than unary operators.

C/C++ unary operators have higher priority than binary operators. 

Operators "==", "!=" have higher priority than logical connectives.

The C++ standard guarantees that the life of a temporary object (if it is **lvalue**) is extended to the life of any reference that refers to it, **including the constant**. 

References to rvalue objects (objects whose address cannot be obtained) do not extend the lifetime of temporary objects. Most likely the compiler won't let you compile. However, the compiler can only detect simple constructions.

If you create a temporary object, and call a method from this temporary object that will return a reference to itself, then the compiler will no longer be able to determine this.
In simple cases, based on this trick, you can capture returned temporary objects by constant reference to reduce the number of copy constructors.

# Call function 
1. A non-constant reference cannot refer to a temporary variable.

2. Although temporary objects can only be passed as `const T&` or `T`. However, calling non-const methods on temporary objects is allowed. The initializer for const T& does not need to be an lvalue and even be of type T. In such cases, a temporary variable is created to hold the initializer, lasting until the end of the scope of the reference.

# Variants of Casting 

`const_cast` - removes `const` and `volatile` modifiers from a pointer.

`static_cast` - casting one type to another using standard or user-defined conversions.

`dynamic_cast` - the argument to dynamic_cast can be a null pointer - the result of this operation is a null pointer. The argument to dynamic_cast must be a polymorphic type, this requirement simplifies the implementation. The result of dynamic_cast need not be a polymorphic type. If it is impossible to understand what the type needs to be converted to (diamond-shaped inheritance with duplicates), a null pointer will be returned. It will also return a null pointer for the simpler base case when casting is failed.

`reinterpret_cast` - force casting instructions

`C-style type casting` - tries to use static_cast, if not, uses reinterpret_cast. Further, if necessary, uses `const_cast`. 

**Private inheritance** - in addition to the invisibility of variables by the user of the derived class of members of the vase class, also does not allow the use of implicit type casting.
```cpp
struct A{int a;};
struct B:private A{int b;};

int main()
{
  B b;
  { A& ba = b;     }  // error
  { A& ba = (A&)b; }  // ok    

  return 0;
}
```

# Glossary

*Upcast.* Cast to the base class.

*Downcast.* Cast to the derived class.

*RValue*. Something from which the address cannot be taken (in 99% of cases these are unnamed temporary variables). And in fact can be encoded in the code of generated instructions for the processor. A good counterexample is something that is an rvalue but has a name `this`.

*LValue*. What is to the left of the operator equals. Each lvalue is implicitly converted to an rvalue.

*XValue*. Something that would be destroyed very soon, and an object for which it is reasonable to use move semantics to take data via `T&&` notation from C++11.

# Linkage
ISO C++2003. 7.5.3: *Every implementation shall provide for linkage to functions written in the C programming language, "C", and linkage to C++ functions, "C++".*

To link in C++ style functions:

```cpp
extern "C++" void f() 
```

Linkage rules cover not only name mangling, but also call convention.

# Data types with special guarantee in memory layout
## Aggregates 
Formal definition from the C++ standard (C++03 8.5.1 §1):
*An aggregate is an array or a class (clause 9) with no user-declared constructors (12.1), no private or protected non-static data members (clause 11), no base classes (clause 10), and no virtual functions (10.3).*

Aggregate types are unique in that objects of such types can be initialized in C++98/03 using the curly brace syntax, just as structures are initialized.

## POD or Plain Old Datatype

An aggregate class is called a POD if it has no user-defined copy-assignment operator and destructor and none of its nonstatic members is a non-POD class, array of non-POD, or a reference.

If you want to write a more or less portable dynamic library that can be used from C and even .NET you should try to make all your exported functions take and return only parameters of POD-types.

The lifetime of objects of non-POD class type begins when the constructor has finished and ends when the destructor has finished. For POD classes, the lifetime begins when storage for the object is occupied and finishes when that storage is released or reused.

For objects of POD types it is guaranteed by the standard that when you memcpy the contents of your object into an array of char or unsigned char, and then memcpy the contents back into your object, the object will hold its original value

As you may know, it is illegal (the compiler should issue an error) to make a jump via goto from a point where some variable was not yet in scope to a point where it is already in scope. This restriction applies only if the variable is of non-POD type.

It is guaranteed that there will be no padding in the beginning of a POD object.


## Standard Layout (Since C++11)

C++11 introduces relaxed POD type definition; new standard layout types. 
To have standard layout the following rules should be satisifed for your type:

* no virtual functions
* no virtual base
* zero or more base classes of standard-layout class types
* no two base classes of the same type
* all data members should have the same access control
* all data members are defined in the most base class or most derived class.
* no restriction for static member functions and static members

# Coroutines

`co_await` - suspend coroutine while waiting for another computation to finish.
`co_yeild` - returns a value from coroutine to the caller. Suspend execution of coroutine, until subsequently calling the coroutine.
`co_return` - return from coroutine. The `return` statement is prohibited in coroutine.

# Concepts
Named requirements to contraint template parametrts.


# References

[1] The C ++ Programming Language Special Edition, B.Stroustrup

[2] The C Programming Language, Harbison Steel

[3] The continuing evolution of C++. Bjarne Stroustrup https://www.youtube.com/watch?v=ooehrkYkGdA
