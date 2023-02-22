---
title: Acccessors and Mutators
description: 
published: 1
date: 2022-08-17T20:09:29.403Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:19.393Z
---

#### Prerequisite Knowledge
- [Encapsulation](/ooDesign/encapsulation)
# Accessors and Mutators

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



#### Practice 
 - Tutorial: [Accessors and Mutators](http://localhost:8888/lab/tree/tutorials/ooDesign/accessorsMutators.ipynb) 

