---
title: Java Hello World
description: 
published: 1
date: 2022-08-17T19:14:07.874Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:44.077Z
---


# Java Hello World



The ``` Hello world ``` program is entrenched as a common first program that people write when learning a new programming language.  In a truly object-oriented language,``` Hello world ```  is more complex than it is in a procedural language.  

#### Procedural Hello World in Java

The Java programming language permits procedural approaches to programming, so the most common ``` Hello world ``` program in java consists of a single static method as shown below.


```
public class HelloWorld {

    public static void main(String[] args) {
        // Prints "Hello, World" to the terminal.
        System.out.println("Hello, World");
    }
}

```
Every Java program must be contained in a class declaration (in this case ``` public class HelloWorld ```. A java program  is run by executing a [specific method called ``` main ```.](/java/mainMethod)  The definition of that method is shown in the example above beginning at ``` public static void main(String[] args) ```.   

#### Object-Oriented Hello World in Java

The object-oriented approach to writing a ``` Hello world``` program is slightly more complicated than the procedural version, but it is a much better illustration of basic OO principles.

```
public class HelloWorld{
    private String message;
    
    public HelloWorld(String theMessage){
				message = theMessage;    
    }

    @Override
	public String toString(){
       return message;
    }

}
````
The example above [defines a class](/ooConcepts/classes) that has a [instance variable](/ooConcepts/variables) that contains the message, a constructor for establishing the message value, and an [instance method](/ooConcepts/methods) for returning the message to the calling program. The instance method is named `toString()` and is a method that every class should have.  What this class does not contain is that [main method](/java/mainMethod) that was previously mentioned.

That main method could go in the same class definition, or in any other class definition. It would look something like this:

````
public static void main(String[] args) {
  HelloWorld theInstance;
  theInstance = new HelloWorld("hi there world");
  System.out.println(theInstance.toString());
 }
````

In the main method example  you can see the declaration of a variable of type HelloWorld followed by the assignment of an instance of that type of object to the variable. Finally the toString method of that instance is called and sent as a parameter to the `println` method. What do you think will be printed?

In general for object-oriented programs written in Java, the main method should not be doing much of the computing or work of the program. All the main method does is set up the environment and start the execution.

Also, the input/output for any object-oriented program should occur in a single class.  All other classes should pass parameters and return values to that class for input/output.


