---
title: Instance Variables
description: 
published: 1
date: 2022-08-17T20:05:43.015Z
tags: instance, private, accessor, mutator
editor: markdown
dateCreated: 2022-08-17T18:15:16.850Z
---

# Instance Variables
* Recall that **instance** is equivalent to **object**
* An instance variable holds a value that exists in exactly one object.

Instance variables are one type of *attribute* that a class can have. They are variables that are local to the definition of the **class**, as opposed to being local to a method. Any instance method that is defined in the class can automatically use the instance variables for that class.

When creating a new class using an OO process, it is best to identify the *messages* (methods) that the class must respond to before trying to identify the variables that will hold the state of the class.  

Once the public methods have been identified, it is easier to understand what types of instance variables the class will need.  

**Each instance variable will have a type:**
  1. Primitive  Type - boolean, char, int, float, etc.
  1. Class Type - Class or Interface (e.g. String, ArrayList)

```
public class Pet{
    private String name; //built in class type
    private Contact owner; //programmer defined class type
    private float age;  //primitive type
}
```

### Accessors and Mutators

Instance variables should be private. There are extremely rare cases where an instance variable might need to be package protected, but those cases will not arise for someone just learning Object Oriented programming. Make your instance variables private.

The mechanisms for allowing inspection and state change are known as [accessor and mutator](/ooDesign/accessorMutators) methods. Such methods are also sometimes called getters and setters. The construction of these methods is discussed in more depth [in a different wiki entry](/ooDesign/accessorMutators).

Consider the skeleton Die class shown below.

```
public class Die
{
	private int numFaces;
	private int faceValue;
  
  public int roll()
  {  
  	//code to roll the die here
  }
  public int getFaceValue() 
  {
  	return faceValue;
  }
  public void setFaceValue(int value)
  { 
  	faceValue = value;
  }
}
```

The faceValue variable in the Die class is called instance data because each instance (object) that is created has its own version of it, also called instance variables, member variables, member data.

To use the Die class, a reference variable of type `Die` must first be created.
![Two die declarations (firstDie and secondDie) and a depiction of the memory created for the reference variable.](/images/referenceDeclaration.png)
When the code that declares the reference variable is executed, a memory location is reserved and labelled with the variable name. The memory location is sized to hold a memory address (reference).

The reference variable can then be set to point at the memory location for an instance of the Die class. The instance is created using the `new` keyword.

![code: firstDie = new Die(); the reference variable from previous image now has an arrow pointing to a box with interior boxes labelled with the Die attributes numFaces and faceValue. There is also a reference attribute in the Die box for a function pointer to the Die class methods.](/images/memoryAllocation.png)


Every time a Die object is created memory is reserved for the instance variables. When a method is used to change the state of the instance, the memory associated with that instance is updated with the new state.


![code: firstDie.setFaceValue(5).  The faceValue attribute space in the box representing the Die object now has the number 5 in it.](/images/instanceVarValues.png)

Notice that the faceValue variable in the two instances noted above now have different values.

> The values of the instance variables define the state of an object created from a class.
{.is-info}



