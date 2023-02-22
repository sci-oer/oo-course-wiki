---
title: Cohesion and Coupling
description: 
published: 1
date: 2022-08-17T19:38:22.172Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:15:24.427Z
---

#### Prerequisite Knowledge
- [OO Concepts](/ooConcepts)

# Software Metrics

Defining *good* for software is challenging because there are so many variables.  Is software good when it works even if it uses a lot of memory or disk space?  Is software good when it is efficient whether or not it accomplishes the task? Is software good when it works correctly but cannot be modified to add new features? There is no definition of *good* with respect to software.

There are, however, many different measures and metrics that can be used to characterize software and those metrics can be used to discuss the quality or suitability of the software in the context of its purpose and use.

Two commonly used metrics for Object Oriented software are **Cohesion** and **Coupling**.

## Cohesion 
Cohesion refers to the number and diversity of tasks that a single unit is responsible for. A *unit* might be a package, a class, or  a method.  If a unit is responsible for one  logical task, we say it has high cohesion.  The more tasks a unit has, the less cohesive it is.

> We aim for high cohesion.
{.is-info}


### Method Cohesion 
Short, single-purpose methods increase cohesion. A method should do exactly one task. If the task needs subdividing, write an additional method and have the first method call the second method.

Parameter list length decreases cohesion. Use instance variables to keep parameter lists short.

Consider the code shown below from a board game program.
```java
    while (checkGameDone == false) {
        //prints out the current state of the board
        printBoard();
        //resets to new move
        checkMove = false;
        //gets input from user
        while (!checkMove) {
            System.out.println(curPlayer.getName() + " Please enter a position number: (1-9): ");
            try {
                move = input.nextInt();
                // calculates the position based on the move they chose/input
                position = getBoardPos(Character.forDigit(move, 10));
                //create token to be played   
                if (curPlayer == players.get(0)) {
                    newToken = new GameToken(curPlayer.getName(), 'X');
                } else {
                    newToken = new GameToken(curPlayer.getName(), 'O');
                }        
                //checks if this move can be made 
                if (isMoveValid(newToken, position) == false) {
                    //error message and loop again
                    System.out.println("Error - Invaid move. Please try again.");
                } else {
                    checkMove = true;
                }
       
            } catch (Exception e) {
                System.out.println("Error - Invalid move. Please try again.");
                input.nextLine();
            }    
        }

```
The method is called `startGame`, but the methods not only starts the game, but it checks the validity of moves, gets input from the player, updates the board after a move and handles errors. As written it is not a very cohesive method.

It can be made more cohesive with a renaming to `playGame()`, and the creation of several more methods. One potential redesign is shown below.

```java
    while (! gameOver()) {
        printBoard();
        curPlayer = getCurrentPlayer();
        while(! curPlayer.moveComplete()){
            newPos = getPlayersMove(messageToPlayer);
            messageToPlayer = makeMove(curPlayer,newPos);
        }
     }
```
The redesigned code is more cohesive because it has one task: to cause the game to be played.   All of the details about how that game is played are encapsulated in other methods, that also have a single task.

One characteristic of a cohesive method is that it usually requires very few comments.   The redesigned method is *self documenting* because the names of the methods called describe what computation is happening.

> **Cohesiveness applies to more than methods**
> - Classes should represent one single, well defined entity.
> - A method should be responsible for one and only one well defined task.
> - packages should be used to groups related classes, not necessarily all the classes for an entire application.
{.is-info}


Avoid **Catch-all** methods. Catch all methods can often be summarized by statements like the following:
- “All of these steps need the same if-then loop so I’ll put them all in one method” 
 - “All of these calculations are needed at this step so we’ll put it in one method so we only have one call”
 - “All of this stuff uses the same data so we’ll put it in one method”
{.is-info}



## Coupling

Coupling is a representation of the number of connections between separate units of a program. Coupling is described using the terms **loose coupling** or **tight coupling**
If two classes depend closely on many details of each other, we say they are *tightly coupled*. 

A class has a *dependency* on another class when it uses some aspect of the second class.  It might have an instance variable of that type or it might instantiate a variable of the class type in a method.  Consider the partial listing shown below.  This listing is from an abstract class  taken from the board game application.

```java
public abstract class Game implements RuleSet {

    private Grid grid;
    private ArrayList<Player> players;

  public Game(int n, int m) {
        grid = new Grid(n, m);
        players = new ArrayList<>();
    }

  public void addPlayer(String name) {
        Player player = new Player(name);
        players.add(player);
    }

  public boolean setCellToken(String TokenName, char TokenValue, int n, int m) {
        GameToken token = new GameToken(TokenName, TokenValue);
        BoardPos position = new BoardPos(n, m);
        return grid.setCellToken(position, token);
    }    
}
```
This class is coupled with several other classes:
  - ArrayList
  - Player
  - String
  - BoardPos
  - Grid
  - RuleSet
  - GameToken
  
Coupling is necessary for an OO program to operate, so we never try to eliminate coupling.  Rather we try to strike a balance between the amount of coupling and maintaining good cohesion.   A class that is completely uncoupled from other classes will not be cohesive.   A design that is excessively cohesive may result in high coupling.  Good design aims for a middle position where coupling is kept to the necessary connections to promote a well encapsulated, cohesive implementation.


Coupling can be visualized using a dependency diagram.   The diagram below shows the dependencies between the classes discussed in the [Using Polymorphism](/ooDesign/usingPolymorphism) resources. The thickness of the line represents the strength of the dependency.   The line colours don't matter for this discussion.

![Dependency diagram of Animal hierarchy](/images/animalExampleDependency.png)
 
All of the classes in that example are in some way coupled to the Animal class, which is understandable since it was an example of using polymorphism.  However, it can be seen that the concrete classes are not coupled to one another as there are no dependencies between them (e.g. there is no line between `Feline` and `Lizard`)

Contrast the previous dependency graph with the one shown below (taken from an implementation of a different game).  This second example shows a more highly coupled design.  For example the `models.managers` package is compled to `models.blocks.chamber` as well as models.blocks.passage and also to `models.blocks.` `chamber` and `passage` are also coupled to `blocks` as well as to one another.   
![Dependency diagram of packages in a game implementation](/images/GameDependencyGraph.png)


> We aim for *loose coupling*.
{.is-info}


Loose coupling makes it possible to understand one class without reading other classes that it may use. Loose coupling allows us to change one class with little or no effect on other classes. Loose coupling increases maintainability of code.


#### Recorded Lecture
[Cohesion and Coupling](/ooDesign/cohesionCoupling)http://localhost:8000/lectures/ooDesign/CohesionAndCoupling/)

#### Practice 

- [Self Study Exercises and Practice Problems](/practiceActivities/ooDesign/cohesionCoupling)  
