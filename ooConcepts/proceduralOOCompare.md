---
title: Procedural Programming vs OO programming
description: 
published: 1
date: 2022-08-17T20:02:07.154Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:11.912Z
---



# Programming Paradigms


### Paradigms
A programming paradigm is simply an approach to decomposing and organizing a solution to a programming problem. No one paradigm is best for all situations. A good programmer should be familiar with several paradigms and comfortable programming in at least two.  
>Programming languages can support a particular paradigm,however, it is up to the programmer to follow the practices.  A choice of programming language does not guarantee a program is written in a particular way.
{.is-info}


Programming paradigms include:

- Procedural Programming
- Object Oriented Programming
- Functional Programming
- Logic Programming
- Parallel Programming

While an exploration of programming paradigms is beyond the scope of this resource, it is sometimes useful to compare a new paradigm (e.g. Object-Oriented) to a known paradigm (e.g. Procedural).

### Procedural Paradigm

When a program is written procedurally the developer first identifies the **processes** that are required to accomplish the goals of the program. Often each of those processes become a function or procedure in the end program, possibly with sub-functions or procedures to help maintain a readable code structure.

A procedural program is somewhat like a recipe. The steps in the solution to the problem are identified and ordered and data is passed from step to step until the solution is reached.

### Object-Oriented Paradigm

Object-Oriented programs consist of a collection of classes that provide mechanisms to manipulate their state. Through calling methods or **message passing**, the classes work together to accomplish the goals of the program.   

When a developer creates an Object-Oriented program they first consider the 'entities' or classes that are represented in the problem description. They identify the capabilities that each of those classes must have by examining each requirement of the program in the context of how each class must be manipulated.

One of the biggest advantages of OO programming is that the resulting classes can be reused in other programs. The creation of an OO program is somewhat similar to creating a reusable library of code. This reusability helps avoid the issue of code being written repeatedly throughout a program.

### OO/Procedural Comparison
The fundamental components of an OO program are classes, attributes and methods. Constructors are a specialized form of method.

|     Object Oriented    |     Procedural    |
|---|---|
|     Class    |     no   real   equivalent:  struct+functions    |
|     Attributes    |     members of a struct    |
|     Methods    |     functions    |
|     Constructors    |     malloc memory for a struct    |



