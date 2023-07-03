---
title: Using References
description: 
published: 1
date: 2022-08-17T19:16:49.710Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:14.396Z
---


# References (Pointers)

Often it is stated that Java is easier than C because it doesn't use pointers. In fact, Java uses pointers for everything, but it seems easier than pointers with C because memory management is handled automatically with no intervention from the programmer.

When a variable of a class type is declared, that variable is, in fact, a pointer. Java programmers use the word *reference*.   

Suppose we have a class defined to represent a Dog.  
The statement `Dog fido;` declares a reference variable that is capable of holding the address of an object of type Dog.

When we assign an instance to that variable with `fido = new Dog();`  we first allocate memory for the instance and then  map the address of the instance to the reference variable.   The call to `new` allocates memory, the call to the class constructor initializes the instance variables, and the assignment operator puts the address into the reference variable. 



`Dog fido`: Tell JVM to allocate space for a reference variable.
    
`new Dog()`:  Tell JVM to allocate space for new Dog object.
    
`=` : Link the instance/object and the reference variable. 
    

Two reference variables can contain the same reference, and therefore point to the same object.

Any change to the object named by one of these variables will produce a change to the object named by the other variable, **since they are the same object**.

Consider the example below.   

```
Dog fido;
Dog fluffy;
fido = new Dog();
fido.setName("fido");
fluffy = new Dog();
fluffy.setName("fluffy");
// check the names
System.out.println(fluffy.getName());
System.out.println(fido.getName());
//assign fluffy to point at the same object as fido
fluffy = fido;
// now what happens?
System.out.println(fluffy.getName());
// predict what happens here too
fluffy.setName("pebbles");
System.out.println(fido.getName());
```
Two reference variables are created and assigned to two different instances (each with their own spot in memory).   Instance data is changed by passing the `setName` message to each of the instances.  

Then one of the reference variables is reset to point at the same instance as the other variable. Now two references point to the same part of memory. One of those references is used to send a message to the instance to change data values via the `setName` method.  This changes the data values for the instance.  Both references are pointing to the same instance, so now the call to `fido.getName()` will return the word *pebbles*.

If you've programmed in C or C++ you have likely noticed that this practice appears to generate lots of memory leaks because the memory isn't deallocated. Java handles all the memory management for you. When there are zero references pointing to an instance, that instance is scheduled for garbage collection and will be freed and placed back on the heap for use.

