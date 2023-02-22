---
title: Instance Methods
description: 
published: 1
date: 2022-08-17T20:05:18.493Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:09.388Z
---

#### Prerequisite Knowledge
- [Classes and Instances](/ooConcepts/classes)
- [Message Passing](/ooConcepts/messagePassing)
- [References to objects](/ooConcepts/references)

# Instance Methods
An instance method can only be executed by making the method call using an instance of the class that defines the method.  Suppose we had defined a `Pet` class that had a method called `doTricks()`. We could call that method by first creating an instance of type `Pet`  with `Pet myPet = new Pet()`.  We could then ask that instance of pet to do tricks by using the reference variable to call the method `myPet.doTricks()`.  

> An instance method requires the object of its class to be created before it can be called.
{.is-info}

#### Method Definion

Method definitions are divided into two parts: **a heading, or signature**, and a **method body**. The method heading identifies the **name** of the method, the **return type** of the method, and any **parameters** that the method takes.   




![Illustration of a method body for a multiplication method](/images/methodHeader.png)

The method body defines the computation of the method. In the example below the method body consists of multiplying the two parameters and returning the result.

![Illustration of a method heading for a multiplication method](/images/methodBody.png)

Methods must either return a value or be declared with `void` as a return type.
The body of a method that returns a value must also contain one or more `return` statements. A return statement is followed by the value to be returned. `void` methods do not require a return statement.


The objects or instances of a class share the memory for method definitions. When instances of a class are created they contain an internal pointer (essentially a function pointer) to each of the instance methods for that class.

![Illustration of memory allocation for instances including function pointer for methods](/images/memoryAllocation.png)

> **There are two types of instance methods:**
>   1. Methods that compute and return a value
>   1. Methods that perform an action on the state of the object (void method)
{.is-info}



#### Practice 
 - Tutorial: [Instance Methods](http://localhost:8888/lab/tree/tutorials/ooConcepts/instanceMethods.ipynb) 

- [Self Study Exercises and Practice Problems](/practiceActivities/ooConcepts/methods) 