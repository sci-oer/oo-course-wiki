---
title: Single Responsibility Principle
description: 
published: 1
date: 2022-08-17T19:39:04.372Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:42.423Z
---


# Single Responsibility Principle

There are many different guidelines for Object-Oriented design. One set of guidelines is known as the **SOLID** principles.  

  - **S**ingle Responsibility
  - **O**pen-closed
  - **L**iskov substitution
  - **I**nterface segregation
  - **D**ependency Inversion
  
The *Single Responsibility Principle* is based on the idea that a module, class, or function is responsible for exactly **ONE** part ofthe program functionality. It goes further to state that the portion of the program should be **ENTIRELY** responsible for that part of the program functionality

The *Single Responsibility Principle* is upheld when programs have good encapsulation and good cohesion.

Responsibilities are the things that a program must do.
Some responsibilities will be very abstract, e.g. play a game. Other responsibilities will be quite concrete, e.g. determine if there is a win condition in the game.
**Responsibility Driven Design** starts by identifying as many of the responsibilities as possible and grouping those responsibilities into classes.


## Worked Example

The example in this section is taken from a software application that helps an adventure-style game author randomly select the contents of a dungeon space. The components in this discussion are specificaly designed to select the types and quantities of treasure in a space.

#### Identified Responsibilities regarding treasure selection
1. choose a type of treasure from the  random treasure type table
1. randomly determine if the treasure has a container
1. randomly determine what the container for the treasure is
1. randomly determine if the treasure is protected by a trap or guard
1. if so, randomly determine what that trap or guard is

##### Code for R1, R2 and R3

In the image below `setDescription()` is responsibile for choosing the treasure type and `setContainer()` is responsible for determining if there is a container and getting the type of container.

There are two easy refactors that will improve this code greatly with respect to single responsibility.
- Duplicate code for randomly determination is seen in both methods.  Neither of the methods should have responsibility for generating random numbers. The duplicate code should be moved to a different method or class.
- `setContainer()` contains code for identifying whether or not there is a trap on the container (yellow highlights in the image). That code should be relocated to a separate method.

![Two methods shown, setContainer and setDescription. setContainer incorrectly also has code for setting other aspects of the treasure item, and the methods both have the same code for generating die rolls. ](/images/singleResponsibility.png)



## Responsibility Matrix
One effective way to identify spots in a program that could benefit from refactoring is to create a matrix that outlines which class in your program accomplishes which tasks.  

The tasks, or responsibilities, that the program must accomplish are listed in the first cell of each row of the matrix. Each class in your program is shown in a separate column. 
A mark in the cell indicates that the class has some responsibility for accomplishing the responsibility.

|           | ContactManager | Contact | Address | History | ... |
| ----------------| :------:| :------:| :------:| :------:| :------:|
| Responsibility1 |    x    |         |         |    x    |         |
| Responsibility2 |         |    x    |         |     x     |       |

The matrix can be used to identify classes that have too much responsibility as well as to identify responsibilities that are shared between several classes. 

If two classes share responsibility, the task is likely too abstract and needs to be subdivided so that one class initiates the task and calls other classes to solve subtasks.

A second type of matrix can be used to help understand the way that responsibilities are divided within a class. One matrix is created for every class, and the rows of the table represent a method. A sample is shown below.

| method sig | responsibility | instance vars used | other class methods called | objects used with method calls | lines of code |
|:----------:|:--------------:|:------------------:|:--------------------------:|:------------------------------:|:-------------:|
|somemethod|this is what it is responsible for| a,b,c|someothermethod|Cat, Feline|14

For each method the signature, its responsibility, instance variables and helper methods, and other objects used in the method are listed.  It is often useful to list the approximate number of lines of code as well.  This type of matrix is very useful to understand which methods in a class may need to be refactored or moved to other classes.


