A tree data structure is a non-linear data structure because it does not store in a sequential manner. It is a hierarchical structure as elements in a Tree are arranged in multiple levels.
-   A tree data structure is defined as a collection of objects or entities known as nodes that are linked together to represent a hierarchy.
-   It's a non linear data structure as it does not store data in a sequential manner, but stores in a hierarchical fashion.


## Terminologies
![[Pasted image 20230220102515.png]]


| Terminology | Description | Diagram |
| --- | --- | --- |
| Root | Root node is a node from which the entire tree originates. It does not have a parent | Node A |
| Parent Node | An immediate predecessor of any node is its parent node. | B is parent of E & F |
| Child Node | All immediate successors of a node are its children. The relationship between the parent and child is considered as the parent-child relationship. | F & E are children of B |
| Leaf | Node which does not have any child is a leaf. Usually the boundary nodes of a tree or last nodes of the tree are the leaf or collectively called leaves of the tree. | E, F, J, K, H, I are the leaf nodes. |
| Edge | Edge is the connection represented by a line between one node to another. In a tree with n nodes, there will be ‘n-1’ edges in a tree. | Connecting line between A&B OR A&C OR B&F OR any other nodes connecting each other. |
| Siblings | Siblings in real life means people with the same parents, similarly in the case of trees, nodes with common parents are considered to be siblings. | H&I are siblings |
| Path | Path is a number of successive edges from source node to destination node. | A ,C, G, K is path from node A to K |
| Height of Node | Height of a node represents the number of edges on the longest path between that node and a leaf. | A, C, G, K form a height. Height of A is no. of edges between A and K,, which is 3. Similarly the height of G is 1 as it has just one edge until the next leaf node. |
| Levels of node | Level of a node represents the generation of a node. If the root node is at level 0, then its next child node is at level 1, its grandchild is at level 2, and so on | Level of H, I & J is 3. Level of D, E, F & G is 2 |
| Degree of Node | Degree of a node implies the number of child nodes a node has. | Degree of D is 2 and of C is 3 |
| Visiting | When you’ve iterated or traversed to a specific node programmatically, accessing value or checking value of the current node is called visiting. |  |
| Internal Node | A node that has at least one child is known as an internal node. | All the nodes except E, F, J, K, H, I are internal. |
| Traversing | Traversing is a process of visiting each node in a specific order in a tree data structure. | There are three types of traversals: inorder, preorder, postorder traversal. |
| Ancestor node | An ancestor or ancestors to a node are all the predecessor nodes from root until that node. I.e. any parent or grandparent and so on of a specific node are its ancestors. | A, C & G are ancestor to K and J nodes |
| Descendant | Immediate successor of a node is its descendent. | K is descendent of G |
| Sub tree | Descendants of a node represent subtree. Tree being a recursive data structure can contain many subtrees inside of it. | Nodes B, E, F represent one subtree. |