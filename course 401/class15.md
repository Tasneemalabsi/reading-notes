# Trees

A tree data structure consists of:

- Node - A Tree node is a component which may contain it’s own values, and references to other nodes
- Root - The root is the node at the beginning of the tree
- K - A number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.
- Left - A reference to one child node, in a binary tree
- Right - A reference to the other child node, in a binary tree
- Edge - The edge in a tree is the link between a parent and child node
- Leaf - A leaf is a node that does not have any children
- Height - The height of a tree is the number of edges from the root to the furthest leaf

### Tree visual structure

![trees](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BinaryTree1.PNG)

### Pseudocode for this traversal of a tree method

`ALGORITHM preOrder(root)`

  `OUTPUT <-- root.value`

  `if root.left is not NULL`
      
      preOrder(root.left)

  `if root.right is not NULL`

      preOrder(root.right)

## Binary trees

*A tree whose elements have at most 2 children is called a binary tree. Since each element in a binary tree can have only 2 children, we typically name them the left and right child.*

![bt](https://media.geeksforgeeks.org/wp-content/cdn-uploads/binary-tree-to-DLL.png)

**A Binary Tree node contains following parts.**

- Data
- Pointer to left child
- Pointer to right child

**Implementation**

`class Node:`

    def __init__(self, data):
        # left child
        self.left = None
        # right child
        self.right = None
        # node's value
        self.data = data

## K-ary Trees

*Traversing a K-ary tree requires a similar approach to the breadth first traversal.*

![kt](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/KaryTree1.png)

If we traversed this tree Breadth First we should see the output:

**Output:** A, B, C, D, E, F, G, H

![enqueue](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthKary1.png)

![dequeue](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-15/resources/images/BreadthKary2.png)

**Pseudocode**

`ALGORITHM breadthFirst(root)`

`// INPUT  <-- root node`

`// OUTPUT <-- front node of queue to console`

  `Queue breadth <-- new Queue()`

  `breadth.enqueue(root)`

  `while breadth.peek()`
    
    node front = breadth.dequeue()
    OUTPUT <-- front.value

    for child in front.children
        breadth.enqueue(child)
        
## Summary

### Types of trees:

- Binary Tree
- Binary Search Tree
- AVL Tree
- B-Tree

### Tree operations:

- Insert − Inserts an element in a tree/create a tree.

- Search − Searches an element in a tree.

- Preorder Traversal − Traverses a tree in a pre-order manner.

- Inorder Traversal − Traverses a tree in an in-order manner.

- Postorder Traversal − Traverses a tree in a post-order manner.

### Trees applications:

- Binary Search Trees(BSTs) are used to quickly check whether an element is present in a set or not.
- Heap is a kind of tree that is used for heap sort.
- A modified version of a tree called Tries is used in modern routers to store routing information.
- Most popular databases use B-Trees and T-Trees, which are variants of the tree structure we learned above to store their data
- Compilers use a syntax tree to validate the syntax of every program you write.


