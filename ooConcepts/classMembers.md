---
title: Class Methods and Variables
description: 
published: 1
date: 2022-08-17T20:06:06.146Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:00.493Z
---

#### Prerequisite Knowledge
- [Instance Methods](/ooConcepts/methods)
- [Instance Variables](/ooConcepts/variables)

# Class Members
Attributes, or members of a class that do not vary with the instance are called **class members**.  In Java class members are denoted with the keyword `static` and are often referred to as **static members**.


## Static/Class Methods
Static methods are usually created to return a value that is related to the overall class or to do a calculation that does not require any sort of state.  

The `Math` class in Java contains several static methods because many mathematical operations don't need to consider the state of an object.  For example,   it doesn’t really make sense to define a whole class to compare two numbers and find the maximum.

To define a class method in java. you put the keyword static in the header after the visibility.

    `public static int max(int A, int B)`

### Using Class Methods
Class methods are invoked using the name of the class instead of the name of a reference variable that points at an instance.
For example:

  `System.exit(0)`  System is a class
  `Math.random()`  Math is a class
  `System.out.println()`

There is no object associated with a class method, so there are no instance variables available to a static method.    

A static method also cannot call any instance methods directly without first creating an instance of the class.

> **A class, or static,  method belongs to its class rather than the instances:**
> `public static int getDaysThisMonth()`
> 
> **Class methods are invoked via their class name:**
> `int days = Calendar.getDaysThisMonth();`
{.is-info}

`public static void main(String[] args)`  is a class method that you have been using since the beginning of this course.  If you add a main method to a class, it cannot access any of the instance variables or instance methods for that class.

## Static/Class Variables 

A static variable is a variable that belongs to the class as a whole, and not just to one object.  There is only one copy of a static variable per class, unlike instance variables where each object has its own copy.  All objects of the class can read and change the same static variable.

> Static variables should be private.
{.is-info}


Static variables are useful for keeping track of counters and state variables related to the entire class.  For example a class variable could keep track of how many instances of a class were active or of which instance has priority

Static methods and instance methods can access a static variable for a class.  

A static, or class, variable is declared like an instance variable, with the addition of the modifier static.

 `private static int myStaticVariable;`
 
 Consider the image shown below.  The `Die` class has been modified to have a static variable called mostFaces.  This variable represents the maximum number of faces of any Die instance in the program. There are two instances represented in this image, both with 6 faces so the mostFaces class variable is set to 6.  
 
 This variable could have been declared with code that looks like this `private static int mostFaces = 0;`
 
![Static variable in the Die class representing the maximum number of sides for any die instance in the program](/images/staticVariables1.png)

In the next image a third instance has been added to the program.  This die instance has 12 sides and the mostFaces variable in the Die class has been updated to a value of 12.   All three die instances will have the same value for mostFaces.

The code for updating the mostFaces class variable would need to be included in the constructor for the Die class to ensure that every time an instance was created, the number of faces of the new instance was compared to mostFaces and that mostFaces was updated if required.

![Static variable in the Die class representing the maximum number of sides for any die instance in the program](/images/staticVariables2.png)


Static variables can be declared and initialized in the same line of code.

 `private static int myStaticVariable = 0;`

If not explicitly initialized, a static variable will be automatically initialized by Java to a default value.

  - boolean static variables are initialized to false
  - Other primitive types static variables are initialized to the zero of their type
  - Class type static variables are initialized to null


## Constants

Constants are also a class or static member but must include the modifier **final**, which indicates that its value cannot be changed.  

 By convention, constant names are upper case, such as `MAX_FACES`.

As with other class members,use the name of its class in place of a calling object when referring to a constant outside of its own class. e.g. `Math.PI`

Because the values of **final** constants are fixed, they must be assigned at declaration.

`private static final MAX_FACES = 20;`

Static constants may be assigned `public` access because they cannot be changed. 

 `public static final int BIRTH_YEAR = 1954;`


#### Practice 
 - Tutorial: [Class Methods](http://localhost:8888/lab/tree/tutorials/ooConcepts/staticMethods.ipynb) 
 - Tutorial: [Class Variables](http://localhost:8888/lab/tree/tutorials/ooConcepts/staticVariables.ipynb) 




- [Self Study Exercises and Practice Problems](/practiceActivities/ooConcepts/classMembers)  


  
  



