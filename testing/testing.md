---
title: Software Testing Intro
description: 
published: 1
date: 2022-08-17T20:13:48.296Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:16:12.077Z
---

#### Prerequisite Knowledge
- [OO Concepts](/ooConcepts)

# Testing and Debugging

Errors that prevent software from compiling correctly are not bugs. They are simply syntax errors that must be fixed.

**Testing** is the process of executing software to disclose errors in the way the software works. Testing begins when software successfully compiles and runs. Testing should occur at the unit level, where small subunits of code are executed and tested. Testing should also occur at the whole-program level where the paths of computation are exercised once the entire program is running.

**Debugging** is the process of fixing errors that are disclosed by testing. The cause of a bug in code is frequently not the same location as the location indicated by incorrect test output.


> Testing searches for the presence of errors.
> Debugging searches for the source of errors.
{.is-info}


## Testing Techniques 
#### Unit testing
- Small sections of the code are tested independently
	- e.g. method, class, package
- Unit testing should be done in parallel with development
- Requires the use of a test harness or support code that can call the methods or classes being tested (e.g. a separate main method for testing)
- A set of tests is created as the software is built and the entire set (suite) is rerun every time the software is changed (Regression testing).
- Ensures that changes don't break existing functionality
  
#### Test automation
- Thorough testing is time consuming and repetitive.
- Regression testing takes time and discipline
- Testing frameworks, such as Junit,  can automate much of the testing overhead
	- All the tests can be run with a single call to the test framework for the application
- Version control systems such as gitlab offer *continuous integration* that can run the tests for a project every time a merge is made to a branch.

#### Functionality Testing
- the overall functionality of the software can be tested after all components are written
- is useful to test the user interface and ensure that the menus and choices activate the proper computation.
- can be automated sometimes
- often conducted by a human following a script
- is very important to create a repeatable process that includes the steps to take and the data to use.
- is a type of *black box testing*


## Debugging Techniques

  Frequently programmers will find themselves debugging code they did not write so one of the first debugging techniques a programmer should learn is the ability to read someone else's code.

Once you know there is a bug, the next step is to find it.  The general method of finding a bug is to inspect the source code and the computation results to locate the place in the code that is producing the incorrect results.  That inspection can be accomplished using a variety of techniques.

###  Manual walkthroughs

A manual walkthrough of the code does not use the computer.  Instead the programmer or a pair of programmers simulates the execution of the code by tracing through the code and doing any necessary calculations by hand.


**Pencil-paper walkthrough**
- An underused, low-tech approach.   
- Step away from the computer
- *Run* the program by hand
- Create a list of all the variables and write down their values as you step through the program
- Make a note of the expected value and the actual value as you go
- Tester must be very careful to do all calculations as written in the code, not as they assume the calculations will be done.
    
**Verbal walkthrough**
- Explain to someone else what the code is doing step by step
  - Point out each section of the code as you talk
  - The other person might spot the error as you talk
  - You might spot the error as you explain it.
- More formal approaches to this are included in many agile software development processes.
  
### Print statements
- Insert print statements in the code to disclose the values of intermediate computations
- A common techqique especially for novice programmers
- Only effective if the print statements are strategically placed.
- Can be hard to read the output as it gets longer
- Turning  the debugging output off and on requires planning.
  - commenting/uncommenting
  - a flag (`if DEBUG print "debugging output"`)
  - a specialized method 
  - a logger class

###  Debuggers
- Debuggers are both language- and environment-specific.
  - Most IDEs have an integrated debugger
- use the debugger to set breakpoints in the code
- Run the code up to the breakpoint
- Can step execution one line at a time
- Can inspect the call stack
- Object  and variable state is inspectable

> Learn to use a debugger
{.is-info}



#### Practice 

- [Self Study Exercises and Practice Problems](/practiceActivities/testing/testing)  
  
