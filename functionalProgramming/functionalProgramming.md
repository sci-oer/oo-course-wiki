---
title: What is functional programming
description: 
published: 1
date: 2022-08-17T20:15:13.976Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:07.430Z
---

# What is functional programming

Functional programming is a style of programming that composes the computation for a program by connecting smaller units of computation (functions) together. It is  different way to think about programming than either Object-Oriented or Procedural programming.  

In a functional program, a function produces a response (return value) based on the parameters (inputs) it was sent, and that return value is used as input to another function.

A key feature of functional programming is that there are no shared variables or structures. Any one function does not modify any variables, objects, or structures that are used by any other functions. This means that objects sent in as parameters  are immutable and that instance variables are not used to store intermediate values.

Functional programming is extremely useful in situations where asynchronous computation is necessary, such as any web-based services. Many modern languages provide at least some functional programming capability, including Java and Python.

Functional programming languages support a set of operations on lists that are used to build up efficient and easy to understand processes for manipulating collections:

- [Filters](/functionalProgramming/functionalFilters)
- [Maps](/functionalProgramming/functionalMaps)
- [Reductions](/functionalProgramming/functionalReductions)

The *Lambda Expression* is a key construct in writing functional programs. In Java a valuable use of lambda expressions is in the creation of [Listeners for GUIs](/functionalProgramming/lambdaListeners).

It is worth your time to understand how to read a functional program and debug it. If you are familiar with the ideas you will not be intimidated when you see functional parts to a program in code you are working on.




