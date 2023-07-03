---
title: this keyword
description: 
published: 1
date: 2022-08-17T20:00:37.636Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:54.897Z
---


# `this` keyword

Recall that one calls methods with a reference variable, a dot, and the name of the method. e.g. `myVariable.methodName()` 

If an instance variable were public (which it should never be) the programmer could access the instance variable using the same dot notation. e.g. `myVariable.someInstanceVariable`.

Occasionally it is necessary to disambiguate variable names with a reference variable when writing methods for a class.  In such a case there is no obvious reference variable.   Consider the code snippet from a `Pet` class shown below.

```java
public class Pet {
  private String name;
  
  
  public void setName(String name){
    name = name; // PROBLEM!!
  }
}
```
The mutator method for the `name` instance variable requires a parameter that has also been called `name`. The assignment statement on line 6 will result in an error because it is impossible to know which name is which even though one of the `name` variables belongs to the object.

Java provides a keyword (`this`) that acts as a reference variable to the current object. It is helpful to think of `this` as an object pointing to itself. In the example above, line 6 can be rewritten as `this.name = name;` and the problem is resolved. The `this` keyword is a reference to the current object, the dot operator followed by the instance variable indicates exactly which bit of memory is being addressed.


`this` must be used if a parameter or other local variable with the same name is used in the method, Otherwise, the variable name will be interpreted as local


## `this` using to call methods

The `this` keyword can also be used to call methods, but usually isn't necessary.  Some programmers like to use `this` consistently in their code.   Note the use of `this` on lines 5 and 8 of the code below.

```java
public class Pet {
  private String name;
  
  public Pet(){
   this.setName("fido");
  }
  public Pet(String name){
  	   this.setName(name);
  }
  
  public void setName(String name){
    this.name = name; 
  }
}
```
The ability to call methods with `this` is especially valuable for encapsulating [constructors](/ooDesign/constructors) in a class. 

Consider the three constructors shown in the code below.  Rather than duplicating code in each constructor, the constructor that initializes all instance variables is called within the code of other constructors using the `this` keyword. In particular look at lines 5 and 8 of the code below.

```java
public class Die{

public Die()
{
	this(6,1);
}
public Die(int sides){
	this(sides,1);
}
public Die(int sides, int initialVal){
  setNumSides(sides);
  setFaceValue(initialVal);
}
protected void setFaceValue(int val){
	faceValue = val;
}
protected void setNumSides(int max){
	numSides = max;
}
}
```
Because `this` is used to call a constructor, no method name is required.


