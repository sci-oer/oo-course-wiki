---
title: Test Cases
description: 
published: 1
date: 2022-08-17T19:46:00.987Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:16:09.633Z
---


# Test Cases

**Test cases** are sets of inputs that are carefully chosen to exercise one possible condition in the code being tested. The correct output is calculated ahead of time by hand, which means that the test case can be used to demonstrate that some part of the software is, or  is not, working properly.

A test case should produce a result that is either clearly correct or clearly incorrect (pass/fail). A test case should be independent from all other test cases so that each test case illustrates exactly one aspect of the software's correct operation.  


>  Each **test case** must be  independent from the others and must result in repeatable behaviour from the software being tested.
{.is-info}



  
## Choosing Test Cases

Test case selection is important for unit testing and for whole system testing.   For the purposes of this course we will focus on unit testing, but the principles are the same for all testing.

Test cases are chosen so that every possible output from a part of the software is seen when all the test cases are used.   The crucial step is to focus on all **possible** outputs, not just on the expected outputs.  

A programmer must understand the expected behaviour of the software extremely well in order to choose an appropriate set of test cases.  

Suppose that we were tasked with designing test cases to test a method that replaced all vowels in a string variable with the consonant that immediately following the vowel in alphabetical order.    We will restrict this method to operating on English language strings.    

The test cases for this method should include a test for every different category of output.  So the first step is to identify the possible categories of output.  Some categories are shown below.


- a vowel at the beginning of a string is replaced properly
- a vowel at the end of a string is replaced properly
- digits are not replaced in mixed character/digit string
- when `y` is used as a vowel it is replaced properly
- the vowel `a` is replaced properly
- the vowel `e` is replaced properly
- the vowel `i` is replaced properly
- the vowel `o` is replaced properly
- the vowel `u` is replaced properly
- an empty string produces no output
- all vowels are replaced correctly


The list of possible correct categories of output is very long for this imagined method because there are six vowels and every category of test exists for every vowel and then for combinations of vowels.

Once the categories of correct output are identified, the programmer identifies input data that will produce that category of output if the program is operating correctly.   It is normally not necessary to have multiple test cases for a single category of output, if those categories have been correctly identified.

Possible test cases for the categories of output identified for the example method are shown in the table below.  As you can see from the table, it can be very difficult to identify test cases that only exercise a single part of the code.  It is very common to identify additional output categories as one is writing test cases.  For example, this set of test categories should include separate categories for multiple word strings (strings with spaces) and for single word strings.


 |||
 |-----------------------------------------------------------|----------------------------------------------|
| all vowels are replaced correctly                         | `The rain in Spain makes for pretty flowers` |
| a vowel at the beginning of a string is replaced properly | `A wet frog hopped on the log`               |
| a vowel at the end of a string is replaced properly       | `Abracadabra`                                |
| digits are not replaced in mixed character/digit string   | `On the count of 3 start running`            |
| when `y` is used as a vowel it is replaced properly       | `Funny bunny`                                |
| the vowel `a` is replaced properly                        | `This is a cat`                              |
| the vowel `e` is replaced properly                        | `This is a tree trunk`                       |
| the vowel `i` is replaced properly                        | `This is a kitten`                           |
| the vowel `o` is replaced properly                        | `This is a dog`                              |
| the vowel `u` is replaced properly                        | `This is a fun trick`                        |
| an empty string produces no output                        |                                              |

Often tests can be improved if they are constructed rather than drawn from real world examples.   For this example problem, a better test strategy is to create nonesense strings that have exactly one characteristic.

The test cases shown below are better designed to avoid interactions.  Some of the categories are too broad to be covered by a single test case (e.g. digits are not replaced in mixed character/digit strings).   In such cases the programmer can either make two categories or can identify multiple test cases.   Either choice can be an appropriate solution.


|                                                           |                        |
|-----------------------------------------------------------|------------------------|
| all vowels are replaced correctly                         | `fagehiwoquryt`        |
| a vowel at the beginning of a string is replaced properly | `abrtswghbc`           |
| a vowel at the end of a string is replaced properly       | `plkjhrwe`             |
| digits are not replaced in mixed character/digit string   | `rwsd54t` and `rea34p` |
| when `y` is used as a vowel it is replaced properly       | `sdfrytr`              |
| the vowel `a` is replaced properly                        | `prtasr`               |
| the vowel `e` is replaced properly                        | `trert`                |
| the vowel `i` is replaced properly                        | `pibnm`                |
| the vowel `o` is replaced properly                        | `wsopxs`               |
| the vowel `u` is replaced properly                        | `funsw`                |
| an empty string produces no output                        |                        |

> To identify test cases
> 1. Identify categories of possible output
> 1. create input that will produce output for each category
> 1. refine input so that it doesn't overlap with other categories as much as is possible
{.is-info}


Once the test cases are identified, they can be used to create a script, or used in an automated testing framework to build a repeatable test suite for the software.




