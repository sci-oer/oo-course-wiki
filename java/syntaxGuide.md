---
title: Java Syntax
description: 
published: true
date: 2022-08-31T00:52:17.588Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:47:54.501Z
---

#### Prerequisite Knowledge
Experience programming in at least one language
[Java Hello World](/java/helloWorld)

# Java Syntax Guide

#### Program Structure
A java program can consist of only one class file, but most programs are constructed from multiple classes.  At least one of the classes must contain a `main` method.  Class definitions usually import other libraries for use in the class.

When learning to program in an OO fashion it is best to stick to putting each class in its own file and to making a separate class with the  main method (the controller in MVC terminology).   Java permits other structures, but simple is best when learning.

A class definition is shown below that would be in a file called SimpleProgram.java.

```java
package demo;
import java.util.ArrayList;

public class SimpleProgram{
// attributes or instance variables
   private String someInstanceVariable;
   private Date someOtherInstanceVariable;
   private ArrayList<String> anotherInstanceVariable;


// a default constructor

    public SimpleProgram(){
       anotherInstanceVariable = new ArrayList<>();
  }
//other methods go here

}
```
A second class definition that uses the first class.  The second class definition contains a main method.
```
package demo;

public class Runner {

public static void main(String[] args){
SimpleProgram theDemo;
theDemo = new SimpleProgram();
//here we would use the instance we just created
}
}
```

#### Syntax Guide

Java syntax is much like C syntax.  Anyone who is somewhat familiar with any of the languages based on C should have no difficulty mastering java syntax.

**Naming Conventions**

Below is a brief summary of java naming conventions as defined by Oracle.  The [full description of these conventions](https://www.oracle.com/java/technologies/javase/codeconventions-contents.html) can be found on the Oracle website.

- Java is case sensitive.  This means that a variable named `myVariable` and one named `myvariable` are two different variables in a Java program.
- CamelCase is used to connect multiple word identifiers (not underscores)
- class names should begin with an upper case letter
- method names should begine with a lower case letter
- program file names should exactly match the name of the class, including case
- instance and class variable names begin with a lower case letter
- constants are denoted with upper case names

**Identifiers**

Identifiers are the names of variables, classes, methods and constantcs.   
- The only allowable characters in an identifier are alphanumerics, the dollar sign and the underscore. 
- Identifiers may not start with a digit (number)
- Identifiers are case sensitive
- Reserved words cannot be used as identifiers

**Reserved Words**
In addition to the reserved words shown below, java provides literal values `null`, `true`, and `false` that cannot be used as variable names.

| | | | |
|---|---|---|---|
| abstract | enum  | new | transient |
| assert  | extends | package | try |
| boolean | final | private | void |
| break | finally | protected | volatile |
| byte | float | public | while |
| case | for | return |  |
| catch | ~~goto (not used)~~ | short |  |
| char | if | static |  |
| class | implements | strictfp  |  |
| ~~const (not used)~~ | import | super |  |
| continue | instanceof | switch |  |
| default | int | synchronized |  |
| do | interface | this |  |
| double | long | throw |  |
| else | native | throws |  |

**Comments**

Java supports both single line and multi line comments.

- `//` begins a single line comment
- `/*` and `*/` are the opening and closing sequences for a multi line comment
- `/**` is the opening sequence for a comment that contains javadoc readable documentation comnents.  Javadoc comments are closed with `*/`

**Primitive Types**
Java provides several primitive types that are not treated as objects. These types are commonly found in most other programming languages.

| :---| :---| :---| :---|
|byte|boolean|char|float|
|double|int|short|long|

Additionally there is an `enum` type that permits definition of enumerations.

**Flow Control**
Java provides many mechanisms for flow control.

```
if(expression){
	code block;
}else{
  code block;
}
```

```
while (expression){
  code block;
  }
```
``` 
for(initialize counter; end condition; increment rule){
   code block;
   }
```
```
//this is known as a for each loop
for(type variableName: collectionInstance){
  code block;
  }
```

```
do{
 code block;
 }while (expression);
```
```
switch (variable){

	case label1: 
         code block;
         break;
  case label2: 
         code block;
         break;
   default:
         code block;
 }
 ```
 **OO related reserved words**

- `this` is a built in identifier that points to the current instance
- 'static' is a modifier that indicates the identifier belongs to a class and is not part of an instance
- `super` refers to the  parent class of the class using the keyword
- `final` is used to designate elements that cannot be changed. It can be used to create constants, methods that cannot be overriden and classes that cannot be extended.
- `instanceof` is an operator that checks to see if an instance is of the type given.  e.g. `if (myVar instanceOf Cat)`
- `abstract` is a modifier that indicates that the method or class is not completely implemented and will need to be implemented by subclasses.
- `class` is the keyword used to define a new class
- `extends` indicates that the class being defined inherits from the class following the word extends.
- `implements` indicates that the class being defined will provide the methods specified in the interface that follows the word implements.
- `interface` is the word used to define a new interface
 
