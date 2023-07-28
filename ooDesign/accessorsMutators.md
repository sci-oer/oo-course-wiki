---
title: Acccessors and Mutators
description: 
published: 1
date: 2022-08-17T20:09:29.403Z
tags: instance variable, member variable, getter, setter
editor: markdown
dateCreated: 2022-08-17T18:15:19.393Z
---


# Accessors and Mutators

The primary goal of encapsulation is to restrict direct access to the internal state of an object, ensuring that it can only be manipulated through well-defined methods. By exposing the internal state through public accessors and mutators, the class has control over how the state is accessed and modified, preventing external code from bypassing validation or business logic.

One key technique for improving the encapsulation of an Object-Oriented program is to use public methods called *accessors* and *mutators* to ensure that the data belonging to a class is valid and accessed appropriately.


Accessor methods allow the programmer to obtain the value of an object's data in a way that is usable by the programmer without endangering the security of the object. The data can be accessed but not changed. The name of an accessor method typically starts with the word get. Accessor methods are also often called 'getters'.

Mutator methods allow the programmer to change an object's data in a controlled manner, The provided input data is typically validated and/or filtered. The name of a mutator method typically starts with the word set. Mutator methods are also called 'setters'.

Accessor and mutator methods are extremely important in OO design because they help to confine the details of a class implementation to the class. For example, suppose we had implemented a Pet class for some kind of Doggie Daycare management system.  

```
public class Pet{
  private String name;
  ...
  //other instance variables
  
  public Pet(String theName){
		setName(theName);
  }
  
  public String getName(){
    return name;
  }
  public void setName(String theName){
    name = theName;  
  }
```
The Doggie Daycare program would be able to get and set the name of any pet instances through the use of the accessor and mutator methods. The code snipped below could be a part of that program.
```
  Pet currentPet = new Pet( "fido");
  ... 
  //more operations here
  ...
  String petsName = currentPet.getName();
```
The benefits of providing accessors and mutators can be easily seen if we further imagine that, for some reason, the `Pet` class required refactoring to take advantage of a new `Identity` class that included the pet's name, colour, breed and size.  A portion of the refactored class is shown below. Note that the accessor and mutator for `name` had to be refactored and the `name` instance variable has dissappeared.

```
public class Pet{
  private Identity details;
  ...
  //other instance variables
  
  public Pet(String theName){
		setName(theName);
  }
  
  public String getName(){
    return details.getName();
  }
  public void setName(String theName){
    details.setName(theName); 
  }
```
The most important thing to notice however, is that the Doggie Daycare code will need zero refactoring as a result of this update.  The Pet class still provides an accessor and mutator for name that are used in the same fashion as always. The underlying implementation has changed, but because of good encapsulation the impact is minimal.


|       |  |
| :---        |    :----:   |
| **Setters (***Mutators***)**     | Allow the programmer to change the value of an object's data
| **Getters (***Accessors***)**   | Object data can be accessed but not changed.   


## Accessors and Mutators for class type variables.
**parts of section were written by ChatGPT**

While accessor and mutator methods can be beneficial for encapsulation by hiding the implementation details, they can potentially break encapsulation when a class type is returned.

However, when a class type is returned from a getter method, it can lead to a breach of encapsulation in the following ways:

1. Modifiability of Internal State:
If the returned object is mutable, external code can modify its internal state directly, bypassing any checks or logic implemented by the class. This breaks encapsulation as it allows modifications without the encompassing class's knowledge or control, potentially leading to inconsistent or invalid states.

2. Exposure of Internal Implementation Details:
Returning a class type exposes the internal implementation details of the encompassing class. This violates the principle of information hiding, which is an essential aspect of encapsulation. External code may start relying on specific implementation details, leading to tight coupling and making it difficult to change the internal structure without affecting dependent code.

3. Loss of Control over State Modifications:
When a class type is returned, the class loses control over how the object's internal state is modified. It becomes challenging to enforce constraints, perform validation, or apply necessary side effects that may be required when modifying the state. This can lead to unexpected behavior and violate the class's intended behavior or invariants.

To maintain encapsulation, it is generally recommended to avoid returning mutable class types directly from getter methods. Instead, you can follow these approaches:

1. Return an Immutable version or a copy:
If the internal state needs to be returned, consider returning an immutable version of the object or a defensive copy to ensure that the original object remains unmodified.

2. Return Immutable Interfaces or Primitives:
Consider returning read-only interfaces or primitives that expose only necessary information without providing direct access to the underlying object. This allows the class to maintain control over the internal state while providing necessary information to external code.

3. Encapsulate Behavior Instead of State:
Instead of exposing the internal state directly, focus on encapsulating behavior within the class. Provide methods that perform specific actions or operations on the internal state, maintaining control over the state modifications.

By carefully considering what is returned from public accessors and mutators, you can preserve encapsulation and ensure that the class retains control over its internal state and behavior.

