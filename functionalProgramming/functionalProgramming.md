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
**parts of section were written by ChatGPT**

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

#### Key differences between Functional Programming and OOP

1. Paradigm Focus:
- Object-Oriented Programming (OOP): OOP is centered around the concept of objects that encapsulate data and behavior. It emphasizes the organization of code into classes and the interactions between objects. Key principles of OOP include encapsulation, inheritance, and polymorphism.
- Functional Programming (FP): FP focuses on the evaluation of mathematical functions and treats computation as the evaluation of expressions. It emphasizes immutability, higher-order functions, and the absence of side effects.

2. State and Mutability:
- OOP: In OOP, objects often have mutable state, meaning their internal data can be modified after creation. Objects can have methods that modify their internal state.
- FP: FP promotes immutability, where data is not modified after creation. Instead of modifying existing data, functional programs create new data structures through pure functions, avoiding shared mutable state and making programs robust and thread-safe.

3. Control Flow:
- OOP: OOP typically uses control structures like loops and conditionals to manage the flow of execution within methods and classes.
- FP:  Instead of explicit control structures, functional programs rely on function composition and recursion to achieve desired outcomes.

4. Data Transformation:
- OOP:  Objects encapsulate both data and behavior, and methods are invoked on objects to modify or access their internal state.
- FP:  Functions take input data and return transformed output, without modifying the original data.

5. Side Effects:
- OOP: OOP allows for side effects, such as modifying mutable state, I/O operations, or accessing external resources.
- FP: FP discourages side effects and encourages pure functions that do not have observable side effects.

6. Composition:
- OOP: OOP achieves code reuse and composition through inheritance and object composition.
- FP: FP achieves code reuse and composition through higher-order functions and function composition. 

It's important to note that modern programming languages often support both paradigms to varying degrees. For example, languages like Java and C# are primarily object-oriented but have incorporated functional programming features. Languages like Haskell and Scala are designed with a strong emphasis on functional programming but also support object-oriented programming. Choosing the appropriate paradigm depends on the problem at hand and the goals of the project.

#### Domains where FP is appropriate

Functional programming is well-suited for certain types of projects and problem domains. 
1. Data Processing and Analysis:
Functional programming excels in data processing tasks, such as data transformation, filtering, and aggregation. Projects involving data analytics, statistical analysis, or processing large datasets can leverage functional programming's focus on immutability, higher-order functions, and declarative style.

2. Concurrent and Parallel Programming:
Functional programming promotes immutability and avoids shared mutable state, which makes it inherently more suitable for concurrent and parallel programming. 

3. Functional User Interfaces (UIs):
Functional programming can be applied to user interface development. Libraries like React in JavaScript or Elm use a functional reactive programming (FRP) approach, where the UI is described as a composition of pure functions reacting to changes in application state. This approach simplifies UI development, enables better separation of concerns, and supports better testing and debugging.

5. Algorithmic Problem Solving:
Functional programming's focus on pure functions, immutability, and recursive algorithms makes it a natural fit for solving algorithmic problems. Projects involving algorithm design, mathematical computations, or simulations can benefit from the clarity and simplicity offered by functional programming. 
