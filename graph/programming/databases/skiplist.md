# Skiplist
Allows efficient search, insertion and deletion of elements in a sorted list. It is a [[graph/programming/data-structures/probablistic|Probablistic data structure]]. 

Elements are organized in layers, with each layer having a smaller number of elements than one below it. The bottom layer is a regular linked list, while the layers above it contain "skipping" links that allow for fast navigation to elements that are far apart in the bottom layer. Skip lists are implemented using a technique called [[graph/programming/techniques/coin-flipping|coin-flipping]]. 

Has speed of O(log n).

Used in [[graph/programming/programs/redis|redis]]

## Sources
- TODO: Watch it https://www.youtube.com/watch?v=2g9OSRKJuzM&pp=ygUIc2tpcGxpc3Q%3D
