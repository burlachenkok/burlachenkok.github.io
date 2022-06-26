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

# What is C++ from point of view of author of that programming Language (B.Stroustroup)
Bjarne Stroustrup in 2010 jokingly describes C++ as a language:
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
1. Basic Guarantee - no leaks and standard libraries supported.
2. Strong Guarantee - either the operation is completed or not.
3. All containers in c++98 provide a basic guarantee. And some operations (for example `std::vector<T>::push_back`) give a strong garantee.

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

Preprocessor macro extensions in C/C++ has the following property. Once a macro call is replaced by an extension, the macro call search process starts from the beginning of the expanded extension for further replacement. 
But during this process, macros that are referenced in their own expansion are not re-expanded and that preprocessor macro extension does not lead to infinite recursion.
`#define sqrt(x) (x<0 ? sqrt(x) : sqrt(-x))`

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

# About used memory for types and it's layout

1. The representation of an object in memory is a sequence of bits. The representation does not have to include all the *bits*, but the size of an object is the number of units of memory that it occupies. 
The amount occupied by one char character is taken as a memory unit. The number of bits in a character is specified in the CHAR_BIT macro in C Language. All objects of the same type by C/C++ rules occupy the same amount of memory.

2. Computers are classified into two categories in the order of bytes in a word:
- Right to left, or Little - Endian -- the address of a 32-bit word matches the address of its least significant byte (Example of CPU architectures are Intel x86, Pentium)
- From left to right, or Big - Endian -- the address of a 32-bit word matches the address of its high-order byte (Motorolla)

3. Some systems support two modes at the same time. In some computers, data can be located in memory at any address, in others, alignment conditions are imposed on certain types.

4. A typical data type to store pointers to some object/data is a pointer. To store (or serialize the value of pointer) in some integer variable, you can use intptr_t. 
The intptr_t integer type was introduced in C99, uintptr_t is sufficient to store a pointer to any data, but formally not to a function.
There is a special value in C/C++ called a null pointer that is equal to a null pointer constant. A null pointer can be converted to any other type of pointer.

5. A null pointer in C/C++ is any integer expression that yields zero. Or such an expression cast into a pointer. The expressions below will not result in a compilation error, as much as we would like to:
```cpp
      void y(int*){}
      y(0);
```
6. In C++11 instead of NULL you can use `nullptr` the keyword that stands to null pointer variable with the type `std::nullptr_t`.

7. When using `union` for a mixture of structures that start the same way, there is guarantee of an identical mapping of component "from this beginning".

8. In C and in C++ the components of variable of structure type has addresses. There are following guarantees:
* The component addresses are in ascending order. 
* The address of the first component is the same as the address of the beginning of the structure. Regardless of what endian the computer has where the program will run.

9. Structs are not allowed to perform comparisons with `==` or with `>`. The fundamental nature of this restriction in C/C++ is due to the fact that for objects there may be holes in their layout from memory filled randomly.

10. In C++, for the definition (not just declaration) of a variable in global scope you can use `extern int a = 0;`. But in fact `extern` is ignored.
It's due to (7.11.6, C++2003) "A name declared in a namespace scope without a storage-class-specifier has external linkage unless it has internal linkage because of a previous declaration and provided it is not declared const. 
Objects declared const and not explicitly declared extern have internal linkage."
It also follows from this paragraph that declarations of non-const variables declared on namespace level have extern linkage by default in C++.

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

Now let's go into sublte technical details.

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
19. If the prototype is controlled by an ellipsis `...`, i.e. function obtain varying argument number, then the usual unary conversions are performed on the operands. Also besides that, `float` is always promoted to `double`.
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

# Overloading

## Functions and operator overloading precedence

1. Exact type matching, or matching achieved by trivial conversion (array name to pointer, function name to function pointer, type T to const T).
2. Conformity achieved by promotion of integral types and promotion of real numbers (char to int, float to double)
3. Correspondence achieved by standard conversions (int to double, double to int), pointers to derivatives to pointers to base classes. Pointers to arbitrary types to pointers to void*
4. Conformity achieved with user-defined transformations
5. Compliance due to ellipsis ...
6. If a match can be achieved in two ways at the same criteria level, the challenge is considered ambiguous and is rejected.

## Template function overloading
Template function overloading searches for a set of suitable specializations according to steps (1-4) below:

1. All specializations that can potentially be called are searched for
2. If any specialization is the more specialized of the two, then the less specialized is discarded.
3. Overloading allowed for functions from step 1-2 and regular functions
4. If a regular function and a template function match equally well, the regular function takes precedence.

If the function passed 1-4 is not found, the call is considered an error

## Rules for resolving the overload of the binary operator x@y. Where x is of type X and y is of type Y

1. If X is a class. Find out if operator@ is defined as a member of class X or a base class of X
2. View operator@ declaration in the context of x@y expression
3. If X is declared in namespace N, look for operator declaration in namespace N
4. If Y is declared in namespace M, look for operator declaration in namespace M

# Namespace lookup rules
A namespace is a named scope. A namespace, unlike a class definition, is open to new features being added to it.

The `using` directive applies more to namespaces than to classes.

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
This mechanism is called an Argument-dependent lookup (ADL). It's very useful, for example, 
when calling some overridden operator on your type in a situation where you decide to define an operator in the namespace your type is in.
Some nuances I've come across: [https://stackoverflow.com/questions/45713667/unqualified-lookup-in-c](https://stackoverflow.com/questions/45713667/unqualified-lookup-in-c)
Various nuances of working with namespaces are covered in appendix [1] B.10, page 924

2. A locally declared name and a name declared with a `using` directive hides a non-local declaration.

3. Local name declaration takes precedence over NS name, but global declaration does not take precedence over variables imported from NS::*

4. Collisions of unused names are not treated as errors

5. Global names are in the "global namespace". It's just global. It differs from all namespaces (including the unnamed one). 
The global namespace differs from those defined through namespace only in that it is not necessary to write its name. 
In fact It's only really worth thinking about it when you need to use ::global_var when you have problem (3). The operator `::` stands for scope extension. 
With this construction, you will always look first in the global namespace first, and then in the namespaces imported in the global namespace.

6. If the name is declared in the enclosing scope or in the current scope, then the name can be used without problems, without a full qualifier.
7. Continuous repetition of a qualifier distracts attention. Verbosity can be eliminated using the declaration:
7.1 Creating a synonym for a variable through `using NS::x;` It's called using declaration.
7.2 Creation of synonyms for all variables from namepspace - through `using namespace NS;`. It's called *using directive*.

8. Placing 7.2 inside another NS opens up the way to combine/mix features from different namespaces.

9. Creating an unnamed namespace implies auto-generation of its name by the compiler, and insertion `using namespace GEN_NAME;` to the source file with that unnamed namespace.

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

13. One subtle addition to function-names. 
Function names obtained from ADL are looked up in the namespaces of their arguments in addition to the scopes and namespaces considered by the usual unqualified name lookup.

# ```typename``` keyword
The typename keyword must be used in three tasks

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
Comment by B. Stroustrup "In some cases a smart compiler could guess, but in general it's not possible"

3. The typename keyword is required if the type name depends on the selected template parameter.
```cpp
template <class T> T findMax(const std::vector<T>& vec){
  typename std::vector<T>::const_iterator max_i = vec.begin();
  for (typename std::vector<T>::const_iterator i = vec.begin() + 1; i != vec.end(); ++i)
  {
    if (*i > *max_i)
      max_i = i;
  }
  return *max_i;
}
```
There is also a very detailed description here about the typename keyword.
[http://stackoverflow.com/questions/610245/where-and-why-do-i-have-to-put-the-template-and-typename-keywords](http://stackoverflow.com/questions/610245/where-and-why-do-i-have-to-put-the-template-and-typename-keywords).

# Class constructor (ctor) and destructors(dtor) computation order

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

4. Working out the body of the destructor
3. Destructor for class members
2. Destructor of direct non-virtual base classes
1. If the object is the object of the "deepest" class in the inheritance graph, then virtual base destructors are called

# Deleting object of incomplete type

Deleting an object with an incomplete type. 
```cpp
class My;
My* ptr;
delete ptr; // undefined behaviour for incomplete types
```
For POD, and for an object without a destructor, something like C-rutime free will be done, which does not need to know about the size of the object. 
In this case you're lucky and you can typically deleted dynaicall y allocated object, but in general it results in undefined behavior. (5.3.5 Delete C++2003).

# Return Value Optimization
Compilers may or may not perform optimization

# Include search order
The original C specification says that the original directory in which the compiled file is located is used to look for a user-defined include file.
The reality is that it is necessary to clarify the rules according to the specification of the toolchain used. Or understand the essence of the experiments.

# Include naming

1. A standard header file whose name begins with the letter ```c``` is equivalent to a standard header file in the C library. (B. Stroustrup, Spec. Edition, p. 487, 16.1.2)
2. For each "C" standard library ```"X.h"``` header file, there is a corresponding C++ standard header file ```<cX>``` in C++.
3. But "X.h" defines function names in the std namespace, and also imports those names into the global namespace.
4. And "cX" defines function names only in the ```std``` namespace. ([1], 9.2.2, page 247).

# C++ variable initialization
1. There are a lot of types of initialization in C ++

```cpp
const int v1(expr);   // direct initialization
intv2 = expr;         // copy initialization
int arr[] = {1,2,3};  // bracket initialization
```

2. Static variables are initialized to zero for the corresponding type. Array and structure variables are initialized to zero if the initialization list is empty.

3. A reference in C++ shall be initialized to refer to a valid object or function. In particular, a null reference cannot exist in a well-defined program.

4. See types of initialization in C ++
zero_initialization
default_initialization
value_initialization
more about initialization: 8.5, 8.5.1 Initializers from C++2003-10-15

5. If for an array or structure the number of initialization values is less than the dimension of the array or structure, the rest of the elements are initialized with the default value for the corresponding type (as in the case of initialization of static variables).

6. In C++98/03 a `union` cannot have as a member an object with a user-defined constructor.

# Predefined identifiers and macros

`__func__` - In C99, a predefined identifier with the name of the current function.

`__LINE__`, `__FILE__` - current line number, and current source file name

`__DATE__`, `__TIME__` - date and time of file translation

`__STDC__ ` - compiler conforms to the C standard

`__VA_ARGS__ ` - only C++ and C99 formally support that. Built-in name that can be used for macros with arbitarily number of argument. When the macro is invoked, all the tokens in its argument list `...`, including any commas, become the variable argument.

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
* ```sizeof(char)``` with all variations of char is always one byte
* ```sizeof(bool)``` and ```sizeof(wchar_t)``` is implementation-defined

4. Also ```sizeof``` of structures in C/C++ is equal to the amount of memory to store all components, space for padding between components, space for padding after structures. 

5. The ```sizeof``` operator applied for array of structures and for other types, the following rule must be full filled: *The size of an array of N elements in bytes is equal to N times the size of the array element.*

6. In C/C++, a function pointer expression can be used to call a function without explicitly dereferencing the pointer, i.e. you can call the function as via using function pointer via `(*f)()` or via ```f()```

# Function nuances

1. There are two kinds of function call: ordinary function call and member function call. A static member function (9.4) is an ordinary function. (С++ ISO/IEC 14882 2003-10-15)
2. In functions with void return types or when return type is absent e.g. in constructors/destructors you can have the absence of a ```return``` statement in a function body. IT is equivalent to an explicit ```return;``` at the end of the function body.
3. But due to (C++2003, 6.6.3) "Flowing off the end of a function is equivalent to a return with no value; this results in undefined behavior in a value-returning function."
4. In C++, the ```main``` function cannot be called recursively.

# Requirements for C++ instructions

1. In C++98/03 uou cannot modify a variable more than once without a sequence point in C++03/98. Sequence point - semicolon, function return, function jump, and some others, please check specification.
2. C++11 introduces the term order of evaluation. The term sequence point is no longer used.


# Exceptions to the one definition rule

You can read about that in details in [1], 9.2.3 p. 248

Two definitions
* Class
* Template
* Built-in function

Acceptable when:
1. They are in different translation units
2. They are identical token by token
3. The meaning of lexemes is the same in both translation units (Checking this is not included in the capabilities of the programming language itself, but is assigned to the toolkit)

All exceptions to the One Definition Rule is described in C++2003, p.23, §3.2/5.

There can be more than one definition of the following things if they appear in different tranlation units:
1. class type (Clause 9)
2. enumeration type (7.2)
3. inline function with external linkage (7.1.2)
4. class template (Clause 14)
5. non-static function template (14.5.6)
6. static data member of a class template (14.5.1.3)
7. member function of a class template (14.5.1.1)
8. template specialization for which some template parameters are not specified (14.7, 14.5.5)

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

2. C programs should not use names that are keywords in C++ if one wants to be compatible with portability
3. C++ style comments (//) only appeared in C99
4. C++ has new operations ```.*, ->*, ::``` which are not in C
5. Different memory for char literal in C and in C++
```cpp
sizeof('a') == sizeof(char) // C++
sizoef('a') == sizeof(int)  // C
```
6. C++ 1998 uses the C89 preprocessor, although the C language has changed: Tradition C, C89, C95, C99, C11

7. Struct tags in C++ are included in the “other names” namespace.
In this space are
* variables
* functions
* typedef names
* enum constants

Therefore ```struct n{}; typedef double n;``` correct in C but not in C++.

7. However, although for C++ type tag names (struct, union, enum) are implicitly declared with using ```typedef```, but still they can be hidden by variables in the same scope ```S S;```
8. C89 allows qualifiers like ```const```, ```volatile```. C99 added ```restrict```, which is not in official specification of C++98/03/?
9. Support of ```varying array``` array. In C99, the last member of a structure can be a flexible array, also possible in C++.
But in C99, but not in C++, there is a ```flexible arrays```. That arrays with a size specified via a non-const variable. In C99, to pass such arguments to a function, use the notation ```void g(int pp[*], int k){}```
10. Different initialization of the char array. In C++, the array must be of sufficient size to hold the "\0" character
```cpp
char a[3]="12"; char aEquiv[]="12";  // ok in C/C++
char a[3]="123";                     // ok in C but not in C++
```
11. C99 has named initializers for structures and positional initializers for arrays, C++ does not.
12. The definition of ```struct``` and ```union``` in C++ have block scope.
13. ```const``` declarations are ```static``` by default in C++, but ```extern``` in C (Appendix C. C++2003)
7.11.6, C++2003:
"A name declared in a namespace scope without a storage-class-specifier has external linkage unless it has internal linkage because of a previous declaration and provided it is not declared const. 
Objects declared const and not explicitly declared extern have internal linkage."
It also follows from this paragraph that declarations of non-const variables declared on namespace level have extern linkage by default in C++
14. C++ declaration ```void f()``` is equivalent to void ```f(void)``` in C. The declaration in C ```void f()``` state that function has an indefinite number of arguments.
15. If the array is multidimensional, then in all cases only the leftmost index can be omitted, in order to be able to determine the size of the array. Also in C99 component-wise initialization is allowed, and that is nor allowed in C++98/03.
16. In C, but not in C++, you can write, although this is strange: ```sizeof(struct S{int a;});```
17. Implicit cast from integer type to enum is allowed in C but not in C++.
C++ 2003-10-15. page 113. 7.2.5: "The type of an enum is an integer type that must support all underlying values. In C, enum has a synonym for int."
18. In C++, converting a void pointer to any reference type requires an explicit cast operation. And in C, this is done implicitly.
19. Unconditional branching through ```goto``` is allowed in the middle of a nested block in C (while initialization of automatic variables is not guaranteed), this is not allowed in C++ in general, but there is an exception.
The exception is for POD types - you may skip their intitialization. However, there are no guarantees for initialization of them.
20. In C++, there are more stringent requirements for inline functions - an ```inline``` function must be declared as such in all source files, in C99 this is not the case.
21. In C++, an ```inline``` function, in terms of code, can have an address and static variables inside, in C it is not allowed.
22. In C99, the compiler must see the function definition, i.e. the function should be defined so that it is inlined in ```*.h```. The compiler can choose to actually what to do:
* inline calls
* not inline
* partially inline.
23. C++ allows declaration in conditions and it's not allowed in C.
24. There is no such type as a reference in C. (References are described in "С++2003, 8.3.2. References")
25. There are no overloaded functions in C
26. C++ has default parameters and they are not allowed in C.
27. In C++ there is a namespace mechanism with namespace and it does not exist in C.
28. In C you can use ```exit()``` and ```abort()``` with no problems, but in C++ the destructors of local objects are not called.
29. Overloading of operators, functions is allowed only in C++.
30. C does not support General-Purpose-Programming with templates.
31. C99 has a predefined identifier ```__func__```. This identifier is implicitly defined by the compiler at the beginning of the function body as static const char ```__func__[] = "function-name"```. Such identifier was absent in C++98/03.
32. In C++ operators that are not presented in C language usually have the highest precedence, except for ```throw``` which is only above the comma operator ```,```.
33. In C, there must be at least one element in the initialization list when a structure or array is initialized. 
34. Prior to C99, i.e. in C89, C89 with extension there was a restriction on where automatic variables can be defined - only at the beginning of a local block. In C++98/03 already you can declare local variable anywhere.

# Templates
1. In addition to type, template parameters also include Non Type Parameters, which can have the type of an integral constant, reference, and a pointer to a given or function. Pointers to data must have an external link type.
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
For more info: please view at “B.13.6 template” in Special Edition, Biern Stroustrup.

## Template syntax remarks
When instantiating a template, starting from C++11 not necessary to make a space in `>>`. In the case of specifying an integral type in a template parameter, and whish to perform right-shift `>>` you should enclose the expression in parentheses. Example of using `>>`:
```cpp
template <class T, int size>
class AA
{};
AA<std::vector<int>>, 2> obj;
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
The `auto` in C++98/03 was an explicity memory type for local objects, but starting from C++11 it's a type, automatically deduced similar to `template` arguments. The difference is that auto works in usual functions for variables and for arrays. For auto, the deduction is identical to the output for `template` function arguments.
```cpp
auto v1(expr); // direct initialization
auto v2=expr;  // copy initialization
int arr[] = {1,2,3};
for (auto x:arr)
{
  printf("%i\n", x);
}
```

Auto can be used jointly with constant volatile type qualifiers (cv) and with reference and pointers. Examples:
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
Range-Based for Loops valid for any type supporting the notion of a range.
One of the following constructions should be valid:
* **obj.begin()** and **obj.end()** 
* **begin(obj)** and **end(obj)**

# Inline fucntion call
Working with inline functions is described here: https://isocpp.org/wiki/faq/inline-functions. So how not to work with inline functions:

```cpp
// inline.cpp
inline void f()
{
     printf("F inline");
}
// inline.h
inline void f();

// main.cpp
#include "inline.h"
int main()
{
  f();
  return 0;
}
```
That lead to `unresolved external symbol "void __cdecl f(void)" (?f@@YAXXZ) referenced in function _main`.

Now how to work with inline functions
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

In C and in C++98/03 there are three representations of signed integers of n bits are allowed for implementation:

* two's complement (twos-complement-notation) [-2**(n-1), +2**(n-1)-1].
Positive numbers are represented in the usual way, the most significant bit of the sign is set to 0
negative numbers are obtained as (reverse bits(number)+1) in ASM instruction notation for x86 sounds like a NEG operation
1000000..000 is the maximum negative number that has no positive equivalent.

* one's complement (ones-complement-notation) [-2**(n-1)+1, +2**(n-1)-1]
Negative numbers are the complement of all bits of the corresponding positive number. In this representation, positive and negative zero are possible.

* signed integer representation (sign-magnitude-notation) [-2**(n-1)+1, +2**(n-1)-1]
The representation of the modulus of negative and positive numbers is identical. The sign of the number is stored in the most significant bit.

# Basic integer types nuances

1. The compiler's use `unsigned` or `signed` in the absence of an explicit type specification is not defined for `char`. The same situation with bit fields.

2. In general, the result of doing a right shift for signed integer types in the case of negative numbers is undefined.
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
5. When using custom conversions via constructors without `explicit` keyword or defined `type conversions` - only one level of implicit conversions is allowed.

# Language operator nuances

1. C/C++ postfix operators have higher precedence than unary operators.
2. C/C++ unary operators have higher precedence than binary operators. 
3. Operators "==", "!=" have higher precedence than logical connectives.

# References

[1] The C ++ Programming Language Special Edition, B.Stroustrup
[2] The C Programming Language, Harbison Steel
[4] The continuing evolution of C++. Bjarne Stroustrup https://www.youtube.com/watch?v=ooehrkYkGdA


# https://sites.google.com/site/burlachenkok/articles/cpp_moments - DONE
# https://sites.google.com/site/burlachenkok/articles/c_and_cpp_difference - DONE
# https://sites.google.com/site/burlachenkok/articles/c99_vars - DONE
# https://sites.google.com/site/burlachenkok/test_snippets_cpp - DONE

# NEXT
# https://sites.google.com/site/burlachenkok/articles/cpp11 (8.0)
# https://sites.google.com/site/burlachenkok/articles/cpp_tricks
# https://sites.google.com/site/burlachenkok/random-notes-about-c17c20
