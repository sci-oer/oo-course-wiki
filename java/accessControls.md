---
title: Access Control
description: 
published: true
date: 2022-08-29T20:11:33.807Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:47:35.082Z
---


# Access Control


## Controlling access to class data and state

One of the fundamental design principles of OO programming is [encapsulation](/ooDesign/encapsulation). Java provides a set of access modifiers that allow the programmer to customize how the data or state of an instance can be changed  and viewed. 


###  Java access modifiers

These modifiers can be used in the defintion of any class to explicitly describe how access to variables and methods should be controlled. The modifiers are valid for both class (static) and instance members of a class.

A modifier is used by placing it in front of the declaration for a variable or method as shown below.

`public void setSomeValue(String someVariable){...}`
`private String someInstanceVariableName`
`protected void someOtherSetter(int aValue)`
`public static void main(String args[])`

1. A designation of `private`  indicates that only the class itself can use the method or variable.
1. A designation of `protected` indicates that  the method or variable can be used by the class, any classes in the same package, and any subclass that inherits from this class.
1. A designation of `public` indicates that  any class may use the method or variable.
1. if  no modifier is used then the method or variable is assumed to be  *package private* which means that the class and any classes in the same package may use the method or field. This is slightly more restrictive than the explicit `protected` designation.

**Instance variables and class variables should be restricted to private access. Constants may be public access.**




### Deciding on access modifiers

|       | **Private** | **Public** | **Protected**|
| :---        |    :----:   |   :----:   |:----:   |
| **Methods**    |  private if used as helper methods  |  public methods form the API of the class | protected methods can be used to support package or library functions|
| **Instance variables**  | all instance variables private | - - | -- |
| **Static variables**| variables are private|- -| - -|
| **Static constants**| --| constants are often public | protected constants help support package cohesion|



 



