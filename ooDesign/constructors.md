---
title: Creating objects using constructors
description: 
published: true
date: 2022-08-30T14:26:22.670Z
tags: default constructor, new, 
editor: markdown
dateCreated: 2022-05-02T19:48:57.144Z
---


# Object creation with constructors

A constructor is a specific type of method that is used to allocate memory and initialize an object when it is created. Java will initialize instance variables to the appropriate *zero* for the variable type if they are not specifically initialized.  

Java creates a *default* constructor automatically for any class that does not explicitly define constructors. The default constructor takes no parameters. If the programmer writes even one constructor for a class, they must also create a default constructor explicitly.

A constructor is written to have  the same name as the class. Constructors do not have a return value.

The Die class shown below contains three different constructors, each taking a different number of parameters. 


```java
public class Die{

public Die()
{
  numSides = 6;
  faceValue = 1;
}
public Die(int sides){
  numSides = sides;
  faceValue = 1;
}
public Die(int sides, int initialVal){
  numSides = sides;
  faceValue = initialVal;
}
}
```

## The keyword `new` 

A constructor is called using the keyword `new`.  e.g. `ClassName objectName = new ClassName(anyArgs);`. The name of the constructor and its parenthesized list of arguments (if any) must follow the new operator.  A constructor cannot be invoked like an ordinary method.

Because the keyword `new` calls a constructor,  if a constructor is invoked again (using `new`), the first object is discarded and an entirely new object is created, even if you use the same variable name.


## Invoking Another Method in a Constructor

The first action taken by a constructor is to create an object with instance variables. 
You may (and should) invoke other object setup methods within the definition of a constructor.  For example, mutator methods can be used to set the values of the Instance variables. It is even possible for one constructor to invoke another using the keyword `this`. This is is very useful for making well encapsulated constructors.   Consider the revised version of the `Die` class shown below.

```Java
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

The two parameter constructor makes use of the mutator methods in the class and the other constructors invoke the two parameter constructor via the keyword `this`.  

Some approaches to OO design suggest that constructors are to be avoided.   Those approaches require a sophisticated understanding of OO design and  are outside the scope of this resource. 

> When designing your classes, try to provide as many different constructors as needed to allow a programmer to initialize the necessary instance variables.  Always provide a zero parameter constructor.
{.is-info}




 
