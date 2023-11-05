# Skip list
Allows efficient search, insertion and deletion of elements in a sorted list. It is a [[graph/programming/data-structures/probablistic|Probablistic data structure]]. 

Elements are organized in layers, with each layer having a smaller number of elements than one below it. The bottom layer is a regular linked list, while the layers above it contain "skipping" links that allow for fast navigation to elements that are far apart in the bottom layer. Skip lists are implemented using a technique called [[graph/programming/techniques/coin-flipping|coin-flipping]]. 

Has speed of O(log n). Skip lists provide a simple and efficient alternative to balanced trees for certain use cases, particularly when the average number of elements in the list is large.

Used in [[graph/programming/programs/redis|redis]].
## How it works

Let's take an example to understand the working of the skip list. In this example, we have 14 nodes, such that these nodes are divided into two layers, as shown in the diagram.

![[attachments/Pasted image 20231105231231.png]]

The lower layer is a common line that links all nodes, and the top layer is an express line that links only the main nodes, as you can see in the diagram.

Suppose you want to find 47 in this example. You will start the search from the first node of the express line and continue running on the express line until you find a node that is equal a 47 or more than 47.

You can see in the example that 47 does not exist in the express line, so you search for a node of less than 47, which is 40. Now, you go to the normal line with the help of 40, and search the 47, as shown in the diagram.


## Sources
- https://www.geeksforgeeks.org/skip-list/
- https://www.javatpoint.com/skip-list-in-data-structure
- TODO: Watch it https://www.youtube.com/watch?v=2g9OSRKJuzM&pp=ygUIc2tpcGxpc3Q%3D