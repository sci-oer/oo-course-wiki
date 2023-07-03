---
title: Using Java Collections
description: 
published: 1
date: 2022-08-17T19:22:04.809Z
tags: 
editor: markdown
dateCreated: 2022-08-17T18:13:31.758Z
---

# Collection Classes

The Java Collections Framework contains many interfaces and abstract classes that facilitate easy development of specialized collections.  However, it also contains several concrete classes that can be used directly in your programs.

The names of the concrete classes in the framework give information about how that collection can be expected to work. For example, the `ArrayList` class is in the `List` family with respect to the collections framework and it has array-like functionality. The `HashSet` class is in the `Set` family of the collections framework and its functionality is based on hashing.

### Parameterized Types
In Java, collections are implemented as parameterized or generic types.   This means that a collection can be created to hold any one type of object. In the examples code below the `ArrayList` files holds objects of type `String` and the `HashMap` called phoneList holds pairs of objects such that the `Integer` object proves an identifier to look up the `String` object. The map example could be used to look up the names associated with a particular phone number.  
```
  ArrayList<String> files;
  HashMap<Integer,String> phoneList;
```
Collections are created by calling `new`.   The type parameter can be inferred from the declaration and does not have to be included in the call to new.   For Example:
`files = new ArrayList<>();`

Collections are used like any other object.  First a reference variable is declared of the correct type, then the reference is assigned to point at an object of that type.  The reference variable is then used to call methods that belong to that object.

```
ArrayList<String> files;
files = new ArrayList<>();
files.add("Hewey");
files.add("Dewey");
files.add("Louis");
/* retrive the first element */
String firstElement;
firstElement = files.get(0);
System.out.println(firstElement); //should print Hewey
/* for-each loop to print out all elements*/
for(String name:files){
	System.out.println(name);
}
```
The enhanced for loop is particularly useful when working with collections.  The syntax is 
```
for (TypeInCollection variableName: referenceToCollection){
		//operations here
}
```
This construct will loop through the entire collection and put a reference to the next object in the collection into the variablename at the beginning of each loop.   It is equivalent to a  for loop with a counter based on the size of the collection.
```
TypeInCollection variableName;
for(int i=0; i < referenceToCollection.size(); i++)
{
   variableName = referenceToCollection.get(i);
   //operations here

}
```

### [ArrayList](http://localhost:8000/docs/api/java.base/java/util/ArrayList.html)

- An `ArrayList` provides list-like operations such as add, remove, get, contains, isEmpty and insert
- The type paramter of an `ArrayList` indicates what kind of objects are stored in the `ArrayList` 
- The `ArrayList`  increases capacity as necessary so it is unecessary for the programmer to directly manipulate the size
- The `ArrayList` keeps a private count of the number of elments in the list that can be accessed with the `size()` accessor method.
- `ArrayList` allows for index-based access to elements. Indexing starts at zero
- `ArrayList` can be navigated with a for-each loop

### [HashMap](http://localhost:8000/docs/api/java.base/java/util/HashMap.html)
- `HashMap` is parameterized with two types.
- Maps are collections that contain pairs of objects.
- The first element of the pairs  is the key and the second is the value.
- The `HashMap` facilitates data lookup works by accepting a key, and retrieving a value.
- `HashMap` provides operations such as put, get, remove, isEmpty, contains
- Elements in a `HashMap` are stored in an order that is appropriate for the map, not necessarily in insertion order.  If you loop through a map, don't rely on the output order to be consistent.
- Example: a phone list.

```
HashMap <Integer, String> contacts = new HashMap<>();

contacts.put("6032340945", "Bugs Bunny");
contacts.put("5198244120", "Samantha Stevens");
contacts.put("9052182876", "Dakota George");

String name = contacts.get("9052182876");
System.out.println(number);
```
The map from the example above can be visualized as a table that consists of two columns and three rows.

| Integer    | String           |
|------------|------------------|
| 6032340945 | Bugs Bunny       |
| 5198244120 | Samantha Stevens |
| 9052182876 | Dakota George    |

The enhanced for loop can be used with a HashMap to retrieve each pair of elements.   Another mechanism for looping through the entire map is to first use the `keySet()` method to get a `Set` representation of the keys in the map, and then use that set in the enhanced for loop to `get` each value from the map.

```
Set<Integer> keys = contacts.keySet();
String currentName;
for(Integer currentKey: keys){
	currentName = contacts.get(currentKey);
  System.out.println(currentName);
}
```

## [HashSet ](http://localhost:8000/docs/api/java.base/java/util/HashSet.html)

Sets ensure that the elements in the collection are unique.  No duplicates are permitted.  This behaviour can be very useful in some situations, such as a student record system where they should never be duplicate student ID numbers.

- The `HashSet` provides add, remove, size, contains, isEmpty operations
- A set does not maintain the order of the elements
- A `HashSet` contains a specific type of object, in a similar fashion ot other classes in the collections framework.

```
import java.util.HashSet;
...
HashSet<String> mySet = new HashSet<>();

mySet.add("one");
mySet.add("two");
mySet.add("three");

for(String element : mySet) {
    do something with element
}

```

A set is also a very useful construct for tasks where the number of unique elements must be determined.  The code snipped below can be used to determing the number of unique words in a line of text.

```
    String inputLine = 
           reader.nextLine().trim().toLowerCase();
    String[] wordArray = inputLine.split(" ");
    HashSet<String> words = new HashSet<String>();
    for(String nextWord : wordArray) {
        words.add(nextWord); 
    }
		System.out.println("The number of unique words is: " + words.size());
```

  