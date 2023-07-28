---
title: Stdout
description: 
published: 1
date: 2022-08-17T20:07:03.890Z
tags: output stream, system.out
editor: markdown
dateCreated: 2022-08-17T18:14:33.067Z
---


# Terminal Output to Users

Providing output to the user is accomplished via a stream, but the programmer doesn't need to interact directly with the stream as the Java language provides built-in classes that simplify the process. 

The most common class used is a static member of the `System` class called `out`.  You likely have already used `System.out` many times in your Java programs.

`System.out` is an instance of the [PrintStream](http://localhost:8000/docs/api/java.base/java/io/PrintStream.html) class.   When a Java program is run, System.out is attached to the default output device for the system (usually the screen) and opened. It is closed automatically when your program exits.  

> You don't have to explicitly open and close System.out.
{.is-info}

The methods you will use most often with System.out include:
- System.out.println(thing to print)
   - prints the argument followed by a newline
- System.out.print(thing to print) 
   - prints the argument without a newline
- System.out.printf(thing to print)
   - formats the argument then prints
   - same syntax as `printf` in C
   - e.g. `System.out.printf("Hello %s!\n", "World");`

#### Assembling a String for output

Often the output that a user needs is a composite of variables and string literals.   Java permits concatenation of strings using the `+` operator and also has a `concat()` method in the [String](http://localhost:8000/docs/api/java.base/java/lang/String.html) class.

For example, `String aString = nameVariable + " is funny.";` produces the same results as `String aString = nameVariable.concat(" is funny.");`

Sometimes simple concatenation is awkward for creating the desired string and, since Strings are immutable in Java, it isn't possible to simply search and replace substrings.   Java provides a class, [StringBuilder](http://localhost:8000/docs/api/java.base/java/lang/StringBuilder.html), that solves this problem.
The StringBuilder class has methods for operations such as appending to a string, replacing characters in a string, and inserting characters into the string.  When the sequence of characters is in the desired state, the StringBuilder class will export the contents to a regular String with the `toString()` method.

> The `StringBuilder` class is in the `java.lang` package which is imported automatically. You don't have to explicitly import to use StringBuilder.
{.is-info}

