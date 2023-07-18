---
title: Polymorphism
description: 
published: 1
date: 2022-08-17T20:10:43.379Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:39.912Z
---

# Polymorphism

* Object Oriented Design relies on the idea of an object being a member of more than one type of object. For example, a variable of type [`ArrayList`](http://localhost:8000/docs/api/java.base/java/util/ArrayList.html) is also of type `AbstractList` as well as type `Object`. This idea is called **polymorphism**

* **Polymorphism** means *many forms* and, when used in the context of OO programming refers to the ability of a single object to behave like other kinds of objects.

> The key understanding is that an instance in your program has more than one type. All instances in Java have at least two types because all classes are also of type `Object`.
{.is-info}


Lets suppose that we are programming an inventory management system for a small convenience store. The store sells packaged food items,  single serve items, household items, frozen items, fast food items

Using the inventory management system, the owners need to be able to calculate required space in freezers and fridges, calculate required shelf space for shelf items, get counts of overall inventory, get counts of sub-category inventory, keep track of shelf life for edible items, etc.

**If we think about these requirements in terms of behaviours that the objects in the system must have,  we get a list of behaviours that includes:**

* `getDimensions() `//for freezer/shelf/fridge space
* `getExpiry()` //for things with limited shelf life
* `getItemSKU()` //get the item identification number
* `getNumberInStock()` //total number of items of this type in stock in the store
* `isCookedInStore()` // for things that are part of the fast food offering
* `isFrozen() `
* `isRefrigerated()`

## Polymorphic behaviour

We could just rely on the programmer to make sure every object type provides the correct methods, but that isn't a very sustainable model.  As soon as a new programmer joins the team, there are likely to be errors. It is better to rely on the compiler to force adherence to the design.  

Through use of the OO language we can tell the compiler precisely which types of objects should be related to other objects and exactly which methods each type of object must have.

A UML diagram of the inventory management system is shown below.   

![Class diagram showing polymorphic relationships. Expirable is an interface. StoreItem is a class.  Food implements Expirable and extends StoreItem. DryGoods is a class that extends StoreItem and implements the Displayable interface ](/images/polymorphismClassDiagram.png =50%x )

Java permits polymorphism through two main avenues: the use of [Interfaces](/ooDesign/interfaces) (not GUIs), and the use of [Inheritance](/ooDesign/inheritance).  

Polymorphic relationships are shown on the diagram by a line ending with a triangle arrowhead. Interfaces are shown in the diagram with dotted borders and dotted connecting lines.  Inheritance is shown when classes are connected with a solid line.   




