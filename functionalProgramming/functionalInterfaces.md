---
title: Functional Interfaces
description: 
published: true
date: 2022-05-20T17:41:09.553Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:46:28.368Z
---

# Functional Interfaces
A functional interface, in Java, is any interface definition that has exactly one abstract method.   

A functional interface can be implemented via a lambda expression if desired. This can be handy if the programmer simply needs an object of the interface type for a short period of time.

The code below defines a functional interface.

```java
public interface SomeFunctionalInterface {
    public int squareANumber( int val);
}
```

If this interface were to be used in some other program, the lambda expression implementaion  of the interface might look like this:

```java
... some code here

//creating a variable of the interface type
SomeFunctionalInterface variableName = (int theParameter) ->  theParameter * theParameter;

//using the interface type object

int theAnswer = theVariable.squareANumber(6);

```
Note that we did not create a class to implement the interface.  That isn't necessary if the interface is functional and if the object doesn't need to be wrapped in other objects.


