---
title: Debugging Strategies
description: 
published: true
date: 2022-08-30T14:27:08.875Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:45:45.091Z
---

#### Prerequisite Knowledge

- [Errors and Bugs](/errors/errorsVSBugs)

# Strategies for Debugging

The amount of debugging required can be drastically reduced by following clean code development practices.  
- Compile the code every few minutes. 
- Keep methods short and single purpose.  
- Change only one thing at a time
- Test as you go

A good rule of thumb is to never be more than 5 minutes out from code that compiles and never more than 20 minutes out from correctly running test cases. That way if you encounter an error or a bug, you'll know where to look.

## Correcting Compiler Errors
If your code isn't compiling, you have **errors** in your code, not bugs. In particular the compiler catches **syntax errors**.  

A compiler can over-report errors because sometimes the first error found will cause it to be unable to read the stream of tokens properly and it will identify other aspects of the program incorrectly as errors.

Only the first error message is truly reliable. Fix one error and then recompile the program. A single missing semicolon or brace can be the cause of multiple errors.

Read the error message carefully. As a minimum it will tell you the file and line number that it believes the error occurs. If you can't find the error on that line, look at nearby lines of code for other syntax errors.


## Debugging tools

The first tool for debugging is a robust set of test cases that are executed routinely when code is changed. A failed test case can tell a programmer what part of the code is not operating correctly and greatly speed up the process of locating the bug.

One very common tool for debuggings is simply printing out the values of variables at various stages of the program.  This process works, but requires that the programmer "clean up" their debugging output before the code is finalized.

Most modern IDEs have an integrated debugger that allows the programmer to execute the program one line at a time and inspect the variable values as that execution occurs.   Integrated debuggers are an extremely effective debugging tool.

## Correcting Logic Errors (Bugs)

Logic errors are more difficult to notice because the program will compile correctly and may even run correctly some of the time.   Thorough testing is the only way to find logic errors.

When a program does not operate as expected, the first action is to isolate the section of code that is causing the behaviour. If you change only one section of the code at a time, and test between every change, you'll know exactly which changes cause the incorrect behaviour.  If not, you'll need to spend some time tracing the operation of the code to determine where the computation is going wrong.



#### Debugging nested calls

Complex, nested expressions are compact and can be easy to read, but they are very difficult to debug because of the nested nature.  When a nested call seems to be the source of a bug, a good strategy is to rewrite the nested call as a series of assignment statements.   For example

```
rect.setLocation(rect.getLocation().translate(-rect.getWidth(), -rect.getHeight()));
```
can be rewritten to be much more debuggable in this fashion.

```
int width = -rect.getWidth();
int height = -rect.getHeight();
Point location = rect.getLocation();
Point newLocation = location.translate(width, height);
rect.setLocation(newLocation);
```



#### Practice 
- [Self Study Exercises and Practice Problems](/practiceActivities/errors/debugging)  

