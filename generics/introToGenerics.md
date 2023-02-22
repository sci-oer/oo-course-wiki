---
title: Introduction to Generic Types
description: 
published: true
date: 2022-08-23T16:52:41.892Z
tags: 
editor: markdown
dateCreated: 2022-08-23T16:52:41.892Z
---

# Generic Types in Java

A generic type is a class that is designed to be a container for other types of objects.  It is written in a way that allows it to hold a variety of types of objects, rather than one specific object.

For example, the classes in the [Java Collection Framework](/dataStructures/collectionsFramework) are generic classes that have all be designed to hold any type of object.    You decide what type of object is being held in the generic class when you write the code that uses the generic class.

#### Structure of a generic class

A generic class is defined using a placeholder `T` instead of a type. Whenever the type would be used as a parameter or as a return value `T` is used instead in the source code for the generic class.  

```java
/**
 * Generic version of a StorageTub class.
 * @param <T> The class type being stored in the tub
 */
public class StorageTub<T> {
    private T stored;

    public void set(T toBeStored){
    this.stored = toBeStored;
    }
    public T getContents(){
     return stored; 
    }
}
```

#### Using a generic class

The `StorageTub` class can be used by simply defining the class type that will go into the tub.

`StorageTub<Book> myStuff;` would declare a reference variable to point at a `StorageTub` object that was able to store an object of the `Book` class.    A call to the `new` operator is done exactly as it is for collection objects: `StorageTub<Book> myStuff = new StorageTub<>()`


#### Multiple Types

A generic class is not limited to one type of parameter.   For example, we could refactor our `StorageTub` class to store two types of objects.   

```java
/**
 * Generic version of a StorageTub class.
 * @param <T> The class type being stored in the tub
 */
public class StorageTub<T,S> {
    private T stored;
    private S secondStored;

    public void setFirst(T toBeStored){
    this.stored = toBeStored;
    }
    public void setSecond(S toBeStored){
    this.secondStored = toBeStored;
    }
    // no accessor methods shown
}
```

###### Type Parameter Conventions

By convention, specific letters are used to indicate the programmers intention for the types that make up parts of generic classes.   

- `E` is use to indicate an element.  You will see this in the javadocs for the classes in the Java Collections Framework.
- `K` and `V` are used to represent  key and value respectively.  
- `N' indicates that the programmer intended the type to be a number.  
- 'T', 'S', 'U', 'V', etc represent any type of object.