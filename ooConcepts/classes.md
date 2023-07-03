---
title: Classes, Objects and Instances
description: 
published: true
date: 2022-09-01T19:15:16.099Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:48:14.927Z
---



# Classes, Objects and Instances


## Classes

The *class* is the core component of an Object Oriented program.  A class represents a concept or element of the domain (e.g. "car", "pet"). The *class definition* is the code written that describes the capabilities of the class. 

A *class definition* consists of source code that provides variables to keep track of the characteristics of the element (e.g. "name", "breed", "age") as well as the definition of functions (called *methods) that are used to change the state of the element.  A class definition(e.g. Pet) is the template used when creating variables that are of that type (e.g. myPetCharlie).

More formally, a class is a programmer-defined type. It defines both state and behavior, where the behavior of the class is defined with methods and  he characteristics are defined through attributes (often called *fields*, *member variables*, or *instance variables*). 

For instance, consider a class to represent a single die (singular of dice), Its state can be defined as  the number of sides it has, and which face is showing. Its primary behavior is that it can be rolled, producing a random number no less than 1 and no greater than the number of sides. We can represent a die in an Object Oriented program by designing a class called Die that models this state and behavior. 

In Java a class is usually in a separate source code file.  The keyword ```class``` is used to tell the compiler you are defining a class and braces ```{}``` are used to enclose the class.

```
public class Die {
//an instance variable
    private int numSides;

//an instance method
    private int roll(){
//code for the method here
}

}
```

> **Procedural Programming Equivalent**
> The procedural equivalent of a class is a struct + companion functions
>{.is-info}

## Objects and Instances

In an Object Oriented program, the class defintion is the template for variables.  The variables are called "objects" or "instances". 

> For the purposes of this course, we will use the terms object and instance interchangeably.  Some sources draw a distinction between the two terms.
{.is-info}

Instances represent ‘things’ from the problem domain. For example: the class definition is for "Automobile" and the instances is “that red car in the parking lot”.

An Object Oriented program can have as many instances of a class type as needed.  Consider, for example, a program that represented the movements of radio-tagged outdoor cats at night.   That program may well contain a class called "Pet" and would likely have many instances of the class during a run of the program.  Instances might have names like "brownBlackCat" or "thirdStreetCat". 

```
Die myVariableOfTypeDie;
Pet myVariableOfTypePet;
Pet myBrownCat;
```

> The class definition is the blue print.
> The instance or object is the variable based on that blue print.
> 





