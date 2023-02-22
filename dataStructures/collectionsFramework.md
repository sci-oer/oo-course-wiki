---
title: Collections Framework
description: 
published: true
date: 2022-08-29T20:18:24.628Z
tags: 
editor: markdown
dateCreated: 2022-05-02T19:45:40.527Z
---

#### Prerequisite Knowledge

- [Data Structures](/dataStructures/collectionsDataStructures)


## Java Collections Framework

Java collections are organized with a set of packages known as the [**Collections Framework**](http://localhost:8000/docs/api/java.base/java/util/doc-files/coll-overview.html).  

The collections framework consists of general purpose implementations of basic data structures such as arrays, trees, and linked lists, along with Interfaces that define more specific behaviours to create more feature-rich data structures.   

The interfaces you are likely to use most often include:
- [Set](http://localhost:8000/docs/api/java.base/java/util/Set.html)
- [List](http://localhost:8000/docs/api/java.base/java/util/List.html)
- [Map](http://localhost:8000/docs/api/java.base/java/util/Map.html)

The interfaces differ in their approach to duplicate data and the order in which the data elements are stored.

| Interface | Ordered | Duplicates | Notes |
| ----------| ------- |------------|-------|
| List      | Yes     | Yes        | access possible, can control insertion position |
| Map       | Can be  | No         | Unique keys inserted into the map. Unique values only |
| Set       | Can be  | No         | Only unique values |
| Deque     | Yes     | Yes        | Usually First In First Out (FIFO) | 
  

It is important to realize that Interfaces cannot be instantiated as objects in a Java program. Rather one must use a concrete class that has implemented that interface. Concrete classes that you may find useful include; 
  - [ArrayList](http://localhost:8000/docs/api/java.base/java/util/ArrayList.html)
  - [LinkedList](http://localhost:8000/docs/api/java.base/java/util/LinkedList.html)
  - [HashSet](http://localhost:8000/docs/api/java.base/java/util/HashSet.html)
  - [TreeSet](http://localhost:8000/docs/api/java.base/java/util/TreeSet.html)
  - [HashMap](http://localhost:8000/docs/api/java.base/java/util/HashMap.html)


The naming of the collections available can be confusing because the second word in the name is the one that specifies the interface.  
  * HashMap is unrelated to HashSet, despite similar names.
  * The second word reveals organizational relatedness.


#### Recorded Lecture
[Java Collections Framework](http://localhost:8000/lectures/dataStructures/CollectionsFramework)

#### Practice 
- [Self Study Exercises and Practice Problems](/practiceActivities/dataStructures/collectionsFramework)

  
