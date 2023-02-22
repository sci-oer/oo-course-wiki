---
title: Headless Computing
description: 
published: 1
date: 2022-08-17T19:26:40.356Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:14:23.319Z
---

#### Prerequisite Knowledge
prior experience with command line operation of computer 

# Displays and Computers

Modern computers are typically connected to an electronic display of some sort such as an external monitor or built in screen. That connected device is used as the mechanism by which the computer produces output that the human operator can observe.

While computers *typically* have some sort of display connected, this is not a requirement. For example, a computer could have a printer as its only output device (common for early computers), or it could exclusively provide output as electronic responses to messages as is common with web services.

A computer with no display must communicate with some other device (such as a printer or a remote connection) in order to provide output.  

# Headless Computing

A computer is said to be **headless** if it has no display monitor, keyboard, or mouse connected directly to it. A headless computer provides output via some protocol (e.g. http or ssh) to a different device that then displays the output to the user.

If you are using a computer over an ssh connection there is a very good chance that you are using a headless computer.   Even if the computer you are using does have a display/keyboard/mouse, by operating it over ssh you are using it as a headless computer.

The docker container that this learning resource resides in is a type of headless computer. You can access the docker container from your host computer, but the docker program is passing the messages from your computer to the container.  Your computer's keyboard, mouse and display are not directly connected to the docker container.

The distinction between headless computing and computing with a connected display becomes very important if you are creating programs with graphical user interfaces. A terminal window, docker container, or ssh session cannot support a graphical interface. The libraries to show the graphics require a graphical display to work.  

This is not to imply that graphical applications can only be run locally.  In fact many graphical applications can use a browser as the display, or provide a virtual display (e.g. nomachine) that can be used from within a bespoke client.

However, for the purposes of this course, the GUI programming portion of the work will require that you have a computer with a display that also has all of the tools in place for developing the program.   

### Multiple Views
  
One common mechanism for providing software that works in both a GUI and a headless environment is to ensure that the software in question has a text-based user interface that can be used over an ssh-like connection as well as a GUI interface that can be used when desired on a computer with a full set of peripherals.

To accomplish this, the software must be designed so that the user interface is simplely a **view** on the software's operations and does not conduct any of the computation required for the software to operate.  This is the fundamental principle behind a design pattern known as **Model-View-Controller**.


#### Recorded Lecture

[Headless Computing](http://localhost:8000/lectures/inputOutput/HeadlessComputing/)