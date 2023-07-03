---
title: Avoid duplicate code
description: 
published: 1
date: 2022-08-17T20:11:01.667Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:29.701Z
---

# OO Design Techniques

## Avoid/Remove Duplicate Code 

Novice programmers will often cut and paste code segments when they realize they need the same functionality in more than one place in their program. Often the only change is the data operated on by the copied code.

Duplicate code decreases cohesion because the same work is done in more than one place. It also makes  code maintenance harder. It can lead to the introduction of inconsistencies and errors during maintenance/modification.

Suppose that you've written a chunk of code that does a complicated calculation. The calculation is something that must be done for several different situations in the program.  In this scenario, suppose further that you duplicated the calculation code in the places that it was needed. Now suppose that the calculation requirements are changed and the code must be modified. The developer who makes those modifications must find every occurence of the cut/paste code in order to ensure that the software works properly.   

Duplicated code can cause inconsistencies in software because updates to the code may not be correctly applied to all copies.

The best way to avoid duplicate code is to use encapsulation. Create a method that provides the necessary computation. Use instance variables to maintain state. Use abstraction to create hierarchies of classes so that shared code is located in the parent class.


