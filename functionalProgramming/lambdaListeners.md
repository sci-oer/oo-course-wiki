---
title: Lambda expressions as GUI listeners
description: 
published: true
date: 2022-08-30T14:29:42.916Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:46:47.082Z
---



# Lambda expressions as GUI listeners

A *functional interface* in java is one that has only a single method for the implementing class to provide.  The `ActionListener` interface for SWING Gui construction is a functional interface.  Functional interfaces can be realized without declaring a separate class. 

You can define a lambda expression as the "class" that implements the listener interface. The notation makes it much easier to cleanly separate GUI code from model and controller code.

The general form of a lambda action listener is shown below.
 `guiComponent.addActionListener(ev -> { actions });`
 
 The actions can be defined inside the braces for the action listener, but an even better solution with respect to single responsibility is to have the lambda expression call a method (or methods) from the controller class.  

```java
JMenuItem openItem = new JMenuItem("Open");
// other code maybe here
openItem.addActionListener(
    (ActionEvent ev) -> { controller.openFile(); }
);
```

When there is only a single action described, and when the type of the initiating object is known the surrounding braces and parenthesis can be eliminated.

```java
JMenuItem openItem = new JMenuItem("Open");
// other code maybe here
openItem.addActionListener( ev -> controller.openFile(););
```




