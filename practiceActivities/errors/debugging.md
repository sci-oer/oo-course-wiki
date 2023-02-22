---
title: Practice Activities for Debugging Strategies
description: 
published: 1
date: 2022-05-03T18:54:31.419Z
tags: 
editor: markdown
dateCreated: 2022-04-08T16:49:45.729Z
---

# Practice Activities for [Debugging Strategies](/errors/debugging)
### Self Study Questions
1. Your code won't compile without error messages?  Is this a bug or an error?
<details>
<summary>click here for one possible answer</summary>
  
Code that doesn't compile has syntax errors and is not necessarily buggy.
  
</details>

2. The code compiles and runs but occasionally you get a result that you didn't expect.  Bug or error?
<details>
<summary>click here for one possible answer</summary>
 Unexpected results during normal operation of a program is indicative of a bug in the logic.
  
</details>

3. What kinds of actions does an integrated debugger allow the programmer to do?
<details>
<summary>click here for one possible answer</summary>
  
Integrated debuggers allow programmers to step through the code execution one line at a time and  view the intermediate values of variables. The programmer can also set breakpoints to allow the code to execute up to the breakpoint and then pause for inspection.
  
</details>


3. Why is the practice of printing out variable values to debug not as desirable as using an integrated debugger?
<details>
<summary>click here for one possible answer</summary>
  
The print statements can be hard to read and they must all be removed before code is delivered to the client.
  
</details>


### Practice Problem


The code found  on your docker container at:
`/course/practiceProblems/errors/pigLatinWithBugs`
is a program that generates a pigLatin version of any phrase it is sent.   

Pig Latin is language game in which the first letter of an english word is moved to the end of the word and the suffix `ay` is added to the word.  So the word "cat" becomes "atcay".   There are special cases for some types of words:  
- consonant blends are moved together (e.g. brook becomes ookbray)
- diphthongs are moved together (e.g. this becomes isthay)
- words that begin with vowels just have 'ay' or 'yay' added to the end (e.g. apple becomes appleyay)

The code you've been given has several bugs.   Try to find the bugs using an integrated debugger (or print statements if you can't use an IDE).
The list of bugs is given to you in the folder with the code, but try to find them yourself first.
