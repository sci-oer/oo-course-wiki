---
title: Software Errors
description: 
published: 1
date: 2022-08-17T19:27:45.757Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:13:42.028Z
---


# Errors

One of the key advantages of software systems is that they are fast and that they always produce the same results give the same input.   However, that advantage is eliminated if the software has errors.   Software that produces the correct results some of the time, is usually worse than having no software at all.

Software errors are categorized in a variety of ways. One categorization that is frequently used is:
- errors that prevent the code from compiling
- errors that produce incorrect results given correct input
- errors that are caused by incorrect input

## Compilation Errors
Compilation errors are often called **syntax errors**. They are a result of incorrectly written code that does not follow the syntax rules of the language being used.

#### Common Syntax Errors

1. Mismatching parentheses or braces
2. Case mismatch in variable names (`Name` and `name` are two different variables)
3. Missing semicolons
4. Mismatching quotations on strings
5. Mismatch of types on assignment (e.g. `String myVar = 1234`)
6. Mismatch of parameter types and arguments when calling methods
7. Trying to invoke a method that doesn't belong to the class type of the object
9. Trying to use  private instance variables directly outside an object

## Logic Errors
Logic errors fall into two sub-categories: errors resulting from correct input and errors resulting from incorrect or unexpected input.

### Errors caused by correct input
Logic errors caused by correct input are often a result of an incomplete specification for the algorithm design. Often the programmer has overlooked some of the possible input values or has misunderstood the expected output for some of the possible cases.  These types of errors are called **bugs**.  

#### Common causes of bugs

- Using assignment as a test of equality (`==` vs `=`)
- Off-by-one errors when indexing 
- Neglecting to use the returned value from a method
- Returning an incorrect value from a method
- Computation that doesn't account for edge cases (null, empty string, negative numbers)

### Errors caused by incorrect or unexpected input

These kinds of errors are often found in situations where humans or external programs are providing input to the software. In normal operations that input will be correct, but sometimes the input is flawed and the software malfunctions. One common example is that a filename is provided for a file that doesn't exist or is unreadable.

Errors caused by unexpected input can only be *anticipated* by the software, they cannot be eliminated. Older computing languages employed *error codes* to indicate when unexpected input had caused problems. A function or method would return a numeric code.  The value of the code indicated to the calling software whether the operation had been successful or not. Error codes work, but mean that all programmers using the code must be well acquainted with the different error code values, and those values changed depending on who had written the software.

Object Oriented languages use [Exceptions](/errors/exceptions) to indicate when input has caused an unexpected result. Exceptions are robust and not tied to one particular implementation.




