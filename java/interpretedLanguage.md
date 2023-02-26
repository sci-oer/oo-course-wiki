---
title: Java Compilation
description: 
published: 1
date: 2022-08-10T16:35:00.221Z
tags: 
editor: markdown
dateCreated: 2022-08-09T14:34:29.056Z
---

#### Prerequisite Knowledge

[Using the Tutorials](/tools/jupyterLabIntro)
# Interpreted Programming Languages


## Compiler vs Interpreter

Some programming languages (e.g. C and C++) are compiled and some are interpreted.   A compiler produces machine code that is created for a specific computer architecture and operating system.  Software that is compiled for one computer/OS pair cannot usually be executed on a different computer/OS pair.

Some programming languages (e.g. python, java, javascript) are interpreted.  An interpreter for a programming language produces output that is closer to machine language than human language but that does not contain specific customizations for operating systems or computer architectures.  This intermediate output is often called *bytecode*.   Any computer that is intended to run the software must have a bytecode interpreter installed for the language the software was written in.

Interpreted languages offer far more flexibility and cost savings for development because  a single code base can produce an executable program for any operating system.   Compiled languages can produce software that executes more efficiently although that extra efficiency is rarely noticeable in consumer software.

Many modern languages, such as python, offer both an interpreter and a compiler and thus can provide the advantages of either type of language.

Java is an interpreted language that, confusingly, uses the term 'compiler' for the software that converts human-readable programs to machine-readable bytecode.

### How a Java program is created and run

The process is shown in the image below

1. Write some source code
1. Run the java 'compiler' on your source code using javac  
1. Javac creates a new bytecode file with a .class extension
1. Copy the bytecode to a computer that has a java bytecode interpreter installed.
1. Run the program

![The process of java code compilation as described in the numbered steps above. A source code file is submitted to the java compiler which outputs some bytecode. The bytecode is run by the java interpreter and the application is available to use](/images/compile_cycle.png)

##### JDK compiler: javac
- To invoke:
`javac source-file-name`
- compiles source-file-name and all classes it depends on
- Example:
`cd C:\subfolder\projectname`
`javac JavaSourceCodeFile.java`

#### Running a java program
- `cd C:\subfolder\projectname`
-  `java JavaSourceCodeFile`
   - note the absence of any file extension
-  the keyword“java” starts the Java virtual machine (JVM).
- The named class is loaded and execution is started.
- Other classes are loaded as needed.
- Only possible if class has been compiled.

> #### how does the system know which method to execute?
>The Java system always executes a method called main with a certain signature:
> `public static void main(String[] args) { ... }` 
> 
> For execution to succeed a main method must exist in the class executed.
{.is-success}






