---
title: Software Testing Intro
description: 
published: 1
date: 2022-08-17T20:13:48.296Z
tags: test cases, junit
editor: markdown
dateCreated: 2022-08-17T18:16:12.077Z
---

# Testing

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





 
  
