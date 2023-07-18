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
**parts of section were written by ChatGPT**

A generic type is a class that is designed to be a container for other types of objects.  It is written in a way that allows it to hold a variety of types of objects, rather than one specific object.

Generic classes provide a  mechanism for creating reusable and type-safe code. Generic classes enable the creation of data structures and algorithms that are not tied to specific data types, promoting a more generic and adaptable design.


Benefits of Generic Classes:
1. Reusability: Generic classes promote code reuse by allowing the creation of classes that can be used with different data types. Instead of writing separate implementations for each type, a generic class can handle a wide range of types, reducing code duplication.

2. Type Safety: By using generics, the Java compiler ensures type safety at compile-time. It enforces that the correct types are used with generic classes, reducing the risk of runtime type errors. This helps catch type-related bugs early in the development process.

3. Abstraction and Flexibility: Generic classes provide a level of abstraction by allowing you to design classes and algorithms without being tightly coupled to specific types. This promotes more flexible and adaptable code that can work with various data types.

4. Readability and Maintainability: Generics enhance code readability by clearly expressing the intent of the code. By using type parameters, it becomes evident which types are expected, making the code more self-documenting. Additionally, generic classes make it easier to maintain and update code, as changes to a single generic class can affect multiple data types.


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

##### When to create generics

There are various scenarios in Java where creating a generic class can be appropriate and beneficial. 

1. Collections and Data Structures:
Java's standard library contains many generic classes for collections, such as `ArrayList<E>`, `LinkedList<E>`, and `HashMap<K, V>`. These classes are designed to work with any type of element (`E`), key (`K`), or value (`V`). By creating custom generic classes for collections or data structures, you can create type-safe and reusable containers tailored to your specific needs.

2. Utility Classes:
Generic classes can be useful when creating utility classes that operate on different types. For example, a generic `Comparator<T>` class can provide a flexible way to compare objects of various types. Similarly, a generic `Validator<T>` class can handle validation logic for different data types.

3. Wrapper Classes:
Sometimes, it's necessary to wrap or adapt objects of different types into a unified interface. In such cases, a generic wrapper class can be created to abstract the underlying types. For instance, a generic `Result<T>` class can encapsulate the result of an operation, irrespective of the specific type of the result.


5. Functionality Extensions:
When extending existing functionality, a generic class can be used to maintain the original behavior while adding type-specific enhancements. For instance, you can create a generic `EnhancedList<E>` class that extends the functionality of the standard `List<E>` interface with additional operations specific to a certain data type.

6. Event Handling:
In event-driven programming, generic classes can be utilized to create event listeners that handle events of different types. This allows for more generic event handling mechanisms.

7. Database Interactions:
When working with databases, generic classes can be used to create reusable components for querying and manipulating data of various types. A generic `Dao<T>` class, for instance, can provide a data access object (DAO) implementation that works with different entity types.


