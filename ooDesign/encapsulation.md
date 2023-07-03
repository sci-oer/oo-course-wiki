---
title: Information Hiding/ Encapsulation
description: 
published: 1
date: 2022-08-17T19:35:24.334Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:32.147Z
---


# Information Hiding/ Encapsulation

**Abstraction and encapsulation are often confused:**

- Abstraction has to do with hiding details at a **design** level  
    - Classes and subclasses
    - Interfaces
- Encapsulation is the process of hiding details at  **implementation** level 
    - for example: the details of how ArrayList.add() is implemented are not necessary to use the method


## Effective Encapsulation
In an OO program, computation is achieved by passing messages between objects (method calls). A well encapsulated OO program is organized as a system of classes that ensure that their data fields are inaccessible to client applications while providing methods to access and mutate, where appropriate, those data fields or values that result from computations on those data fields.

Encapsulation can be accomplished through the use of design approaches such as: 
   - private variables
   - private helper methods
   - public methods for all operations required to use the class
   - including toString and equals
   - restricting the public API to only required methods
   
