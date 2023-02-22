---
title: Stdin
description: 
published: 1
date: 2022-03-04T15:34:34.775Z
tags: 
editor: markdown
dateCreated: 2022-02-08T15:16:14.284Z
---

# Practice Activities for [Getting Keyboard Input](/inputOutput/stdin)


### Self Study Questions
1. What is the name of the constant in the `System` class that references the input stream of the keyboard?
<details>
<summary>click here for one possible answer</summary>
  
`System.in`

</details>

2. What class does Java provide to simplify the reading of text input streams?
<details>
<summary>click here for one possible answer</summary>
  
The Scanner class.
</details>

3. Look at the [javadocs for the Scanner class](http://localhost:8000/docs/api/java.base/java/util/Scanner.html).  What method(s) will allow you to set the delimiter used to separate tokens?  What is the default delimiter?
<details>
<summary>click here for one possible answer</summary>
  
The method is `useDelimiter`. There are two versions of it, one that takes a String and one that takes a Pattern.   The default delimiter is whitespace.

</details>

### Practice Problem

Augment the *MadLibs*  program that you wrote for [Output Practice](/practiceActivities/inputOutput/stdout) so that it asks the user for words that belong to a category and then outputs the nursery rhyme with the user's words substituted for other key words in the rhyme.   

A solution to this practice problem can be found on the drive of your course docker container at `/course/practicProblems/inputOutput/madLibsUser`