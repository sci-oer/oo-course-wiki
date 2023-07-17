---
title: Message Passing
description: 
published: 1
date: 2022-08-17T19:17:35.322Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:06.037Z
---



# Message Passing

**Message Passing** in an Object-Oriented program is the mechanism for executing instance methods that are associated with a particular object or instance.    The concept is similar to making function calls, but the method is executing using the specific data or state of the associated instance.

#### Message Passing Example
Imagine that you have three companion animals in your home: a dog, a rabbit, and a bird.    When it is time to feed the animals all three of them will eat, however, they will eat in vastly different ways.   The dog may eat a bowl of kibble, the rabbit might eat a pile of hay and the bird will eat birdseed.  In this example the action of *eating* can be considered the message and each of the three animals is an instance that is executing its own *eat* method.

If we modelled this example as a program we might end up with a `Pet` class:

```
public class Pet {
	//some instance variables here
  private String foodType;
  
  //some constructors here
  
  //some accessors/mutators here
  public void setFoodType(String food){
     foodType = food;
  }
  public void eat(){
  	System.out.println("I am happily munching on " + foodType);
  }
}
```
And then if we were using that class to make a program representing our companion animals it might have a section that looked something like this:

```
Pet bunny = new Pet();
bunny.setFoodType("hay");
Pet dog = new Pet();
dog.setFoodType("kibble");
Pet bird = new Pet();
bird.setFoodType("birdseed");
...
bird.eat();
dog.eat();
bunny.eat();
```
The **message passing** in this example occurs when we call the *setFoodType* method for each instance and again when we call the *eat* method for each instance.  

> The most important concept about message passing is that the execution of the method only impacts the specific instance that calls the method.
{.is-info}


Programmers create a class so that it can recieve and respond to a specific set of *messages*. Then some other class uses the class just created.

Message passing is nothing more than calling a method that is associated with an instance and asking the instance to do something with its state (or data).

Built in Java classes and libraries come with a wealth of methods that can be called to manipulate the state of objects of those types.  

For example, suppose we have a `String` variable `myString` with the value *"Today is a good day"* and we need to know how long it is. 

The procedural way to determine the length is to loop through the string until we get to the end and increment a counter for each letter. This approach requires that the procedure manipulates the variable's data.
  
The Object-Oriented way to find the length of the string is to send a *message* to the string variable(instance) to ask it what its length is with the `legnth()` method like this:

`String myString = new String( “Today is a good day”);`
`int lengthOfString = myString.length();`

The public instance methods of a Java class make up the possible messages that can be passed to an instance of that class.  By convention Java programmers use [Javadoc](/tools/javadocs) comments to identify those methods and create documentation about their use.   This e-text contains a copy of the [javadoc comments for the Java programming language](http://localhost:8000/docs/api/index.html) to help you learn about the possible messages that can be passed to the built in Java classes.

