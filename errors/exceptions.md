---
title: Exceptions
description: 
published: 1
date: 2022-08-17T19:29:20.396Z
tags: try, catch, throw, exception
editor: markdown
dateCreated: 2022-08-17T18:13:44.740Z
---


# Exceptions
Java, and most other OO languages, use *exceptions* to give programs the ability to handle unexpected events. Often these events are precipitated by some kind of input/output such as user input or opening a file.

Exceptions, or unintended events, can occur for a number of reasons including:
- Logic errors made by the programmer
- A user has entered an invalid data.
- A file that needs to be opened cannot be found.
- The program loses connection to a server.

A program is written such that the part of the code that is at risk of experiencing an unexpected event is isolated and a process for handling the error that caused the event is established. If an exceptional event occurs, the event is captured because of the isolation and the error handling code is executed. If there is no execptional event, the error handling does not execute. This process is called *Exception Handling*.

## Exception Handling

In Java, the class [Exception](http://localhost:8000/docs/api/java.base/java/lang/Exception.html) is used to instantiate an object that wraps an error event that occurred within a method. The Exception object contains:
- Information about the error including its type
- The state of the program when the error occurred
- Optionally, other custom information

**Exception Handling** in Java is a powerful mechanism to handle the runtime errors so that normal flow of the application can be maintained. Exceptions are handled through the use of `try`, `catch` and sometimes `finally` blocks to wrap the code that may produce exceptions and define mechanisms for handling the unexpected. 

Java will not let you compile code that can result in exceptions that you have not handled, either through `try/catch` or throwing the exception as part of the method definition. 

### Try/Catch

You may have already used exception handling as you learned about the different mechanisms for input and output in Java. The process of opening a file and reading the contents requires that exceptions are handled.

```
    Path path = FileSystems.getDefault().getPath(location, fileName);
    try {
      BufferedReader myReader = Files.newBufferedReader(path);
      String oneLine = myReader.readLine();
      System.out.println(oneLine);
      myReader.close();
    } catch (IOException e) {
      //terrible exception handler
      System.out.println(e);
    }
 ```
In the example above note that lines 3-6 are enclosed in the `try` block.  The methods that could throw an exception in that block are  `newBufferedReader()` and `readLine()`. `newBufferedReader` throws an `IOExceptions` if there is an error as does `readLine`. The javadocs provide information about the exceptions thrown by a method.

Line 8 of the example is wrapped in the `catch` block of exception handling. That block of code executes if an exception occurs but is skipped otherwise. In this example, the block is designed specifically to handle an instance of `IOException`. Normally an exception handling block does something to fix the problem and help the program resume execution. Printing the exception to the console is useful for learning but not for production software.

#### General form for exception handling

Exceptions can only be handled if some portion of the code produces an exception. In Java this is called *throwing* an exception.
Methods that contain some operation that is at risk of error can communicate that risk to client applications by advertising that the method throws an exception. Often the exception types are tailored to the type of error that causes the exception (such as an `IOException` for file related errors).

Suppose that some class you were writing had a method that did some computation that might throw an exception.   

```
public SomeClass{
//instance variables
...
//other methods and constructors
...

/* Method that does something that risks an error
The method must declare that it might throw an exception
as well as indicate the kind of exception it throws */

public void mightThrowException() throws BadException
{
// other computation here
...
	if (the error occurs ){
  /* when the exception is thrown the execution of the method
  terminates and control is given to the calling method */
		throw new BadException(); 
	}
}

}
```
##### Using a method that throws an exception

If you are writing code that consumes a method that might throw an exception, your code must either handle the exception or rethrow it.

To handle the exception you enclose the call to the method in a `try/catch` block.

```
//other code here
...

try {
	anObject.mightThrowException();
 	}
	catch (BadException ex){
	   System.out.println("Aargh!");
	   ex. printStackTrace(); //printStackTrace is one of the methods of the Exception class.
	}
```
If your code has no way of recovering from the exception, it may be better to pass the exception up to the code that called your code.  You can do that by throwing the same exception.

```
public void aMethodInYourCode()  throws BadException{
//other code here
...
/*calling the method that might throw the exception
because this method also throws the exception, we don't need to try/catch it here */
	anObject.mightThrowException();
}
```
It is usually better to handle exceptions where they occur rather than to pass them up to the next caller.

> - The calling method must catch what the called method throws. 
> - The method that throws the exception has to declare that it might throw an exception
{.is-info}



## Multiple Exceptions 
There are multiple exception classes and programmers can define their own exceptions. A method can throw more than one kind of exception.  This feature is useful to handle each of the possible exceptional situations appropriately.

The example below shows a class called laundry that has a method that could throw either a PantsException or a TShirtException.

```
public class Laundry
{
  public void doLaundry() throws PantsException, TShirtException
  {
    //code that could throw either exception
   }
}
```
The code snippet below shows how those two exceptions can be caught individually to allow for different remediation to occur depending on which exception has been thrown.

```
  Laundry laundry = new Laundry();
  try {
	laundry.doLaundry();
  }
  catch (PantsException pex){
      // take stuff out of pockets of pants
  }
  catch (TShirtException tex){
    // add stain remover to shirt
  }

```


## Hierachy of Exceptions
The more specific exceptions, such as `IOException` are subclasses of the more general `Exception` class.  When a programmer defines their own exceptions, they must also be subclasses of the general Exception class.   A possible set of exceptions based on the Laundry example is shown in the diagram below.

![Exception hierarchy for exceptions in Laundry code sample. ClothingException is the most abstract. PantsException and ShirtException are subclasses of ClothingException.  TshirtException and DressShirtException are subclasses of ShirtException.](/images/exceptions.png)

The hierarchical relationship means that a subclass is also a member of the more general class.  For example,  `ShirtException` and `TShirtException` are subclasses of the `ClothingException` class.  This means that an object of type `TShirtException` is also a `ClothingException`.  


In a situation where  a program has multiple catch statements and the catch statement for `ClothingException` is placed before the catch statements for `ShirtException` and `TShirtShirtException` the program will execute the handler for the `ClothingException` and will never get to the specific catch statements for `ShirtException` and `TShirtShirtException`.

The example below will always execute the catch block on line 4 regardless of what type of exception is thrown.
```
try {
        laundry.doLaundry();
    }catch (ClothingException ex){ 
        // do something to recover from exception here
    }catch (ShirtException e){
        // check washing instructions
    }catch (TShirtException t){
      // add stain remover to shirt
    }
```

The order of the catch clauses has been fixed in the next example so that a TShirtException will be handled if thrown as will a ShirtException and all other exceptions will be handled by the more general catch block.
 ```
 try {
        laundry.doLaundry();
    }catch (TShirtException t){ 
        // do something to recover from exception here
    }catch (ShirtException e){
        // check washing instructions
    }catch (ClothingException ex){
      // add stain remover to shirt
    }
```

> always catch the most specific exceptions first
{.is-success}

## Programmer Defined Exceptions

Programmers often define their own exception classes to make the semantics make more sense.  Self-documenting code is highly readable so that the reader can tell what is happening even without comments.

To define your own exceptions you create a new class (in its own file) and extend the exception class.

## Try with Resources

Because many exceptional situations occur when interacting with an external resource like an input device or file, it is important to ensure that the resource is properly closed if the exception cannot be handled.

One way to ensure that resources are closed is to use the optional `finally` block in a try/catch statement and explicitly close the file in the finally block.

```
try{
  // code that might throw an exception here
   }catch (IOException e) {
     //code to deal with the exception if it happens here
   } finally {
      //code to close the resource here
    } 
```
A slightly more readable method of ensuring that open resources are closed is to use what is called a *try with resources*.   The syntax of this construct is the same as any other try/catch with the addition of an argument that opens the resource that will be used.   


In the example below there is no need to explicitly close the file stream because it has been opened as a resource as part of the try/catch statement.

```
  try (BufferedReader myReader = Files.newBufferedReader(path)) {
      String oneLine = myReader.readLine();
      System.out.println(oneLine);
    } catch (IOException e) {
      //terrible exception handler
      System.out.println(e);
    }
```

 
