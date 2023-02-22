---
title: Gradle
description: 
published: true
date: 2022-08-22T15:02:45.777Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:50:37.040Z
---

# Gradle

Gradle is a build automation tool known for its flexibility to build software. Gradle is used to automate the creation of applications. The building process includes compiling, linking, and packaging Java code. 

## Using Gradle
Gradle is a program that must be installed on your computer, but in regards to this course it has already been installed in the docker container. Gradle works by reading a file that contains the instructions for each build process. Here is where the Gradle file is in the project hierarchy:

![image of the standard project hierarchy for the build.gradle file](/images/gradlehierarchy.png)

Here is what that file looks like:

![image of the build.gradle file](/images/gradlecheckstyle.png)

Gradle can be run from the command line or from the IDE, but there are cases where the IDE will change your Gradle file, so it is best to stick to the command line for this course. Please note that if you submit a Gradle file that does not work on the command line with your assignment, we will **NOT** grade your assignment.

## Running Gradle on the Command Line
Below is an example of the Gradle command line output of a program you have been provided called *HelloWorld*:

![gradle command line output](/images/gradlecommandline.png)

As you can see with the Gradle file provided to you in the examples, the target `gradle run` will not actully run the program but instead it will just be printing out the java command to run the program.

## GradleW

GradleW is a wrapper program used to ensure that there are no versioning issues with shared repositories using gradle.  It is invaluable in a production environment where many developers work in the same codebase.  

There are significant advantages to using the wrapper as it removes the requirement for gradle to be installed on the development machine. However, it adds enough size to the repository that it is impractical for a teaching situation where hundreds of similar repositories must be downloaded to the computer of the person doing the grading.    

Because of the size added by gradlew, for this class we're going to stick with using the installed version of gradle.  It is already installed in the docker container so you don't have to install on your host computer.
> Under **NO** circumstances, should you be adding gradlew and its associated files to your submissions.
{.is-warning}
