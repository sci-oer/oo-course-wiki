---
title: Lambda expressions as GUI listeners
description: 
published: true
date: 2022-08-30T14:29:42.916Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:46:47.082Z
---

#### Prerequisite Knowledge
- [OO Concepts](/ooConcepts)
- [Functional Programming](/functionalProgramming/functionalProgramming)
- [Functional Interfaces](/functionalProgramming/functionalInterfaces)

# Lambda expressions as GUI listeners

The `ActionListener` interface for SWING Gui construction is a functional interface.

This means that you can define a lambda expression as the "class" that implements the listener interface. The notation makes it much easier to cleanly separate GUI code from model and controller code.

The general form of a lambda action listener is shown below.
 `guiComponent.addActionListener(ev -> { actions });​`
 
 The actions can be defined inside the braces for the action listener, but an even better solution with respect to single responsibility is to have the lambda expression call a method (or methods) from the controller class.  

```java
JMenuItem openItem = new JMenuItem("Open");​
// other code maybe here
openItem.addActionListener(​
    (ActionEvent ev) -> { controller.openFile(); }
);
```

When there is only a single action described, and when the type of the initiating object is known the surrounding braces and parenthesis can be eliminated.

```java
JMenuItem openItem = new JMenuItem("Open");​
// other code maybe here
openItem.addActionListener( ev -> controller.openFile(););
```



#### Recorded Lecture
[Using Lambda Expressions as GUI Listeners](http://localhost:8000/lectures/functionalProgramming/LambdaExpressions/)

#### Practice 
  
- [Practice Activities](/practiceActivities/functionalProgramming/lambdaListeners)
