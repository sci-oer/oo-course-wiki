---
title: Polymorphism via Interfaces
description: 
published: true
date: 2022-08-29T20:19:20.564Z
tags: abstraction, polymorphism,semantics
editor: markdown
dateCreated: 2022-05-02T19:49:16.153Z
---


# Polymorphism via Interfaces

An **Interface** is the mechanism Java provides to allow objects to be grouped together when they have similar functionality, but not an obvious parent-child relationship.  Many OO programmers feel that the use of Interfaces is better programming practice than over use of Inheritance.  

> An interface lets the programmer group together objects that have common features but not an obvious hierarchical relationship. 
{.is-info}

For example, an interface called `Edible` could be used to group together all elements of an adventure game that could be eaten by the adventurer.  This might include food items, some plants, small animals and maybe even paper items.  An interface called `Tossable` could be used to group together all elements that could be thrown by the player such as weapons, books, flasks, articles of clothing and gemstones.

A Potion could be both `Edible` and `Tossable`

A key benefit of interfaces is that you can implement multiple interfaces in one class.   Interfaces are Java's answer to the difficult problem of multiple inheritance.
If the implemented interfaces have constants with the same name, but with different values an inconsistency will occur and the code will not compile.  Another type of inconsistency will occur if the interfaces contain methods with the same name but different return types.  
> If a class definition implements two inconsistent interfaces, then that is an error, and the class definition is illegal and will not compile.
{.is-info}


## Using an Interface

You  add an interface to a class you are defining by using the `implements` keyword followed by the name of the interface in the class definition. e.g. `public class SomeClass implements SomeInterface {`.  If more than one interface is implemented, each is listed, separated by commas.  The class implementing an interface MUST provide an implementation for all methods from the interface. That implementation is said to **override** the method and should use the @override annotation in the code.

For example, the Java language provides the [`Comparable` interface](http://localhost:8000/docs/api/java.base/java/lang/Comparable.html) that is used in sorting algorithms.
The Comparable interface contains a single method that must be implemented in order to fulfill the interface implementation `public int compareTo(Object other);`
- The method `compareTo` must return
  - A negative number if the calling object "comes before" the parameter other
  - A zero if the calling object "equals" the parameter other
  - A positive number if the calling object "comes after" the parameter other
- If the parameter `other` is not of the same type as the class being defined, then a `ClassCastException` should be thrown

The programmer is free to define what is meant by 'comes before'. Any reasonable notion of "comes before" is acceptable. All of the standard less-than relations on numbers and lexicographic ordering on strings are suitable.
The only restriction is that the ordering must be a total ordering that satisfies the following rules:
  - (**Irreflexivity**) For no object `o` does `o` come before `o`
  - (**Trichotomy**) For any two object `o1` and `o2`, one and only one of the following holds true: `o1` comes before `o2`, `o1` comes after `o2`, or `o1` equals `o2`
  - (**Transitivity**) If `o1` comes before `o2` and `o2` comes before `o3`, then`o1` comes before `o3`
- The "equals" of the `compareTo` method semantics should coincide with the `equals` method if possible, but this is not absolutely required

Below you can see a revised `Pet` class that implements the `Comparable` interface. Note how the compareTo method is constructed to adhere to the three rules of total ordering. The method will order any two pets by age first, and then by name if their ages are the same.   We can use the `compareTo()` method of the `String` class because that class also implements the `Comparable` interface.

```java
public class Pet implements Comparable{
  private String name;
  private String age;
    ...
  //getters and setters not shown for brevity
  ...
  
  public int compareTo(Object other) throws ClassCastException {
  	if(! other instanceOf Pet) {
        throw new ClassCastException("object is not an instance of Pet")
    }
    int compared = other.getAge() - getAge();
    if (compared == 0) {. //pets are the same age
       compared = getName().compareTo(other.getName());
     }
     return compared;
    
  
  }

}
```
#### Interface Semantics Are Not Enforced
The word *semantics* refers to the meaning of something. 
The java compiler and run-time system check the syntax of the interface and its implementation.  However, neither checks for consistent with its intended meaning. Required semantics for an interface are normally added to the documentation for an interface.  It then becomes the responsibility of each programmer implementing the interface to follow the semantics.  If the method body does not satisfy the specified semantics, then software written for classes that implement the interface may not work correctly.   For example, if the `compareTo` method defined for the `Pet` class randomly returned positive or negative numbers, the compiler and run-time system would accept it as being correct but it would not function as intended.


## Writing a custom interface

The syntax for defining an interface is similar to that of defining a class except the word interface is used in place of class.  An interface specifies a set of methods that any class that implements the interface must have. It contains method headings and constant definitions only. It contains no instance variables nor any complete method definitions.

Because interfaces often describe behaviours, the name of an interface should convey the behaviour.  We often use names like *Comparable*, *Tossable*, *Edible* for interface names.

Below is an example interface for objects in a dungeon game that are edible.   
```
public interface Edible{
    public  double caloricValue(double gramsConsumed);
    public  double chanceOfIllness();
}
```

An interface and all of its method headings should be declared public. They cannot be given private, protected, or package access.  When a class implements an interface, it must make all the methods in the interface public.

An interface can contain defined constants in addition to or instead of method headings.  Any variables defined in an interface must be public, static, and final.  Because this is understood, Java allows these modifiers to be omitted but it is still good practice to include them. Any class that implements the interface has access to these defined constants.

Because an interface is a type, parameters and return types can be interface types





  

