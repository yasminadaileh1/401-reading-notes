# Trees

## Common Terminology
1. Node 
2. Root
3. Left Child 
4. Right Child 
5. Edge 
6. Leaf 
7. Height 

### Sample Tree 
![BinaryTree1](./img/BinaryTree1.png)

### Traversals

**Traversing a tree** allows us to **search** for a node, **print** out the contents of a tree. There are two **categories** of traversals when it comes to trees:
- Depth First
- Breadth First

### Depth First

**Depth first** traversal is where we prioritize going through the depth (height) of the tree first. There are multiple ways to **carry out depth first traversal**, and each method changes the order in which we search/print the root. Three methods for depth first traversal:

Pre-order: `root >> left >> right`
In-order: `left >> root >> right`
Post-order: `left >> right >> root`

![tree-example](./img/tree-example.png)

traversals would result in different **paths**:

Pre-order: `A, B, D, E, C, F`
In-order: `D, B, E, A, F, C`
Post-order: `D, E, B, F, C, A`

 Here is the pseudocode for this traversal method:
 ```
ALGORITHM preOrder(root)

  OUTPUT <-- root.value

  if root.left is not NULL
      preOrder(root.left)

  if root.right is not NULL
      preOrder(root.right)
 ```

 Pre-order means that the `root` has to be looked at first. In our case, looking at the root just means that we output its value. When we call `preOrder` for the first time, the `root` will be added to the call stack:
![DepthTraversal1](./img/DepthTraversal1.png)

Next, we start reading our `preOrder` function’s code from top to bottom. The first line of code reads this:
```
OUTPUT <-- root.value
```

### Traversal Pseudocode

**Pre-order**
```
ALGORITHM preOrder(root)
// INPUT <-- root node
// OUTPUT <-- pre-order output of tree node's values

    OUTPUT <-- root.value

    if root.left is not Null
        preOrder(root.left)

    if root.right is not NULL
        preOrder(root.right)
```

**In-order**
```
ALGORITHM inOrder(root)
// INPUT <-- root node
// OUTPUT <-- in-order output of tree node's values

    if root.left is not NULL
        inOrder(root.left)

    OUTPUT <-- root.value

    if root.right is not NULL
        inOrder(root.right)
```

**Post-order**
```
ALGORITHM postOrder(root)
// INPUT <-- root node
// OUTPUT <-- post-order output of tree node's values

    if root.left is not NULL
        postOrder(root.left)

    if root.right is not NULL
        postOrder(root.right)

    OUTPUT <-- root.value
```

## Big O

The Big O time complexity for inserting a new node is `O(n)`. Searching for a specific node will also be `O(n)`. Because of the lack of organizational structure in a Binary Tree, the worst case for most operations will involve traversing the entire tree. If we assume that a tree has `n` nodes, then in the worst case we will have to look at `n` items, hence the `O(n) `complexity.

The Big O space complexity for a node insertion using breadth first insertion will be `O(w)`, where `w` is the largest width of the tree. For example, in the above tree, `w` is 4.

A “perfect” binary tree is one where every non-leaf node has exactly two children. The maximum width for a perfect binary tree, is `2^(h-1)`, where `h` is the height of the tree. Height can be calculated as `log n`, where `n` is the number of nodes.