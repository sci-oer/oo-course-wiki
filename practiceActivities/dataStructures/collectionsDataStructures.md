---
title: Practice Activities for Collections
description: 
published: true
date: 2022-06-02T16:30:27.213Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:49:35.699Z
---

# Practice Activities for [Data Structures and Collections](/dataStructures)

 - Tutorial: [Using ArrayList](http://localhost:8888/lab/tree/tutorials/dataStructures/ArrayList.ipynb) 
 - Tutorial: [Using HashMap](http://localhost:8888/lab/tree/tutorials/dataStructures/HashMap.ipynb)
  - Tutorial: [Using HashSet](http://localhost:8888/lab/tree/tutorials/dataStructures/HashSet.ipynb)
  
  ### Practice Problems
  
  1. Create a java class called `LootList` that could be used as part of a suite of tools for managing 'dungeon' style games.  The `LootList` class should  use an ArrayList to store all of the items found in the dungeon.   The `LootList` class should provide methods for adding loot, removing loot, and searching for loot based on the name (a string).    Also create a `Loot` class that has, as a minimum, the capacity to get/set a name, a description, and a type.  Type can be an `enum` that includes potion, scroll, wand, jewellery, weapon, armour, etc.    Finally create a Runner class that demonstrates the capabilities of the `LootList` class.
  *A solution to this problem can be found on your docker container at /course/practiceProblems/dataStructures/allTheLoot*
  1. Create a java class called `LootLookUp` that could be used as part of a suite of tools for managing 'dungeon' style games.   The `LootLookup` class should use a HashMap to store all of the items found in the dungeon. Set up your HashMap so that it facilitates searches on either the name or the description of the `Loot` item.   The `LootLookup` class should provide methods for adding loot, removing loot, and searching for loot based on the name (a string) or on the description (a different string).   Start with the same `Loot` class as described in question 1 but add any features you need to it.  Create a Runner class that demonstrates the capabilities of the `LootLookup` class.
    *A solution to this problem can be found on your docker container at /course/practiceProblems/dataStructures/lootInfoLookup*
    
   1. Create a java class called `DungeonLoot` that could be used as part of a suite of tools for managing 'dungeon' style games.   The `DungeonLoot` class should use a HashSet to store items available in the dungeon.  The use of the HashSet will ensure that each possible item is represented exactly once as it will prevent duplicate entries.    The `DungeonLoot` class should provide methods for adding loot, removing loot, and printing out the list of loot sorted by name.   Start with the same `Loot` class as described in question 1.  Create a Runner class that demonstrates the capabilities of the `DungeonLoot` class.  Be sure to demonstrate its ability to prevent duplicate items.
    *A solution to this problem can be found on your docker container at /course/practiceProblems/dataStructures/uniqueItems*  