---
title: Unit Testing
description: 
published: true
date: 2022-08-29T20:14:15.103Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:50:27.168Z
---


# Unit Testing

Unit testing is intended to validate small parts, or units, of source code. A unit is any small testable part of an application. For Java applications a unit is often a class with each method considered as a sub-unit.

Unit testing consists of formal, repeatable tests that are designed for specific classes and methods. Each unit of an application has its own tests. Unit testing should be created in parallel with development.  Testing isn't something that should be done after the software is completed.
 
 
>  Early repeatable testing saves programmer time overall and has the advantage that a test suite is built up and can be used for regression testing when software is modified.
{.is-info}



### Writing Unit tests

Unit tests are created after the [Test Cases](/testing/testCases) are identified. A program called a **test harness**  or **test framework** is created that is used to execute the software being tested and provide the test cases. The test harness methodically invokes each test case and provides a report of which cases have passed and which have failed. Often a framework such as [Junit](/tools/junit) is used.

Suppose we were creating tests for a method that replaces all vowels in a string variable with the consonant that immediately following the vowel in alphabetical order. Some suggested [test cases for this method were identified in a separate wiki page](/testing/testCases).  Further suppose that this method exists in a class called `StringChanger` and the method is called `stripVowels`. Our test harness for one of the test cases might look something like the code shown below.

```java
StringChanger tester;

//check for vowel a replacement

tester = new StringChanger("prtasr"); //the test case
String output = tester.stripVowels();
if (output.equals("prtbsr")) {  // the known to be correct value
     // count it as a passed test
  } else {
     // count it as a failed test
 }
```

A similar segment of code would be written for each test case and the overall test harness would need to have some mechanism for counting and reporting on successes and failures.

This testing code would be run every time a change is made to the `stripVowels` method to ensure that the change hasn't broken previously working functionality.

Fortunately, most programming languages have testing frameworks, like [Junit](/tools/junit),  that provide all of the functionality for counting and reporting on tests.  The programmer still needs to identify the test cases and the correct output but much of the work of building tests is provided with the framework.

### Unit tests with Junit

Because testing frameworks provide tools to manage unit testing, most of the work is in creating individual test methods for each test case.  Testing is more effective if each test case is executed in a single testing method.

The typical process is to create a test class in parallel with each application class.   Continuing with our current example we would have a `StringChanger` class as well as a `StringChangerTest` class.    Within the `StringChangerTest` class each test case becomes a method.   Junit relies on `@Test` **annotations** to identify test cases.

The code shown below accomplishes the same task as the test harness shown previously.   Junit provides assertions that can be used to determine if the output is correct and it handles all of the record keeping for tests passed and failed.


```java
public class StringChangerTest {
	private StringChanger tester;
  
@Test
public void stripVowel_a_test(){
    tester = new StringChanger("prtasr"); //the test case
    assertEquals(tester.stripVowels(), "prtbsr")
}

//more test methods would be needed to test the rest of the stripVowels method

}

```

Running a suite of junit tests is usually handled by build tools such as gradle or maven.  It is also possible to run the tests programatically from your own application.


> It is worth your time to learn to use a unit testing framework.
{.is-info}



