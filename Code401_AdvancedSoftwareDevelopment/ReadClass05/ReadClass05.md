# Reading_Notes
## Implementation: Linked Lists




By [Ghaida Al Momani] (https://github.com/GhaidaMomani).

>>>>>Welcome to Code 401.
<br/>
<hr/>
<br/>


## Description
**What is a Linked List?**

A Linked List is a sequence of Nodes that are connected/linked to each other. The most defining feature of a Linked List is that each Node references the next Node in the link.

There are two types of Linked List - Singly and Doubly. We will be implementing a Singly Linked List in this implementation




<br/>

# Linear data structures

One characteristic of **linked lists** is that they are linear data structures, which means that there is a sequence and an order to how they are constructed and traversed. We can think of a linear data structure like a game of hopscotch: in order to get to the end of the list, we have to go through all of the items in the list in order, or sequentially.

 ![image](../assests/linear.jpg)
<hr/>
    <p align="right">(<a href="#top">back to top</a>)</p>

# Terminology:
**Linked List** - A data structure that contains nodes that links/points to the next node in the list.

**Singly** - Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.

**Doubly** - Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.

**Node** - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.

**Next** - Each node contains a property called Next. This property contains the reference to the next node.

**Head** - The Head is a reference of type Node to the first node in a linked list.

**Current** - The Current is a reference of type Node to the node that is currently being looked at. When traversing, you create a new Current variable at the Head to guarantee you are starting from the beginning of the linked list.


## What does it look like
![image](../assests/linked-list.jpg)



**so to sum up the Parts of a linked list**

The starting point of the list is a reference to the first node, which is referred to as the **head**.
 The end of the list isn’t a node, but rather a node that points to **null**, or an empty value.
![image](../assests/parts.jpg)


<hr/>
    <p align="right">(<a href="#top">back to top</a>)</p>

# Traversal

When traversing a linked list, you are not able to use a foreach or for loop. We depend on the Next value in each node to guide us where the next reference is pointing. The Next property is exceptionally important because it will lead us where the next node is and allow us to extract the data appropriately.

The best way to approach a traversal is through the use of a while() loop. This allows us to continually check that the Next node in the list is not null. If we accidentally end up trying to traverse on a node that is null, a NullReferenceException gets thrown and our program will crash/end.

When traversing through a linked list, the Current variable will tell us where exactly in the linked list we are and will allow us to move/traverse forward until we hit the end.

Traversal Example
Let’s put a use case on our traversal. We want to check whether or not our LinkedList Includes a specific value.

The pseudo-code for an Includes is as so:

```
ALGORITHM Includes (value)
// INPUT <-- integer value
// OUTPUT <-- boolean

  Current <-- Head

  WHILE Current is not NULL
    IF Current.Value is equal to value
      return TRUE

    Current <-- Current.Next

  return FALSE

```

<hr/>
    <p align="right">(<a href="#top">back to top</a>)</p>
  <br/><br/>

<p align="right">Ghaida Al Momani, Software Engineer</p>
<p align="right">Jordan, Amman</p>
  <p align="right">22, 09 MAR </p>