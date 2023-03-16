# Construct Binary Tree from Inorder and Postorder Traversal

 A programming problem where it's required to construct a binary tree given an array of its inorder and postorder traversal

## Problem Statement

Given two integer arrays `inorder` and `postorder` where `inorder` is the inorder traversal of a binary tree and `postorder` is the postorder traversal of the same tree, construct and return *the binary tree*.

**Example 1:**

![](https://assets.leetcode.com/uploads/2021/02/19/tree.jpg)

**Input:** inorder = [9,3,15,20,7], postorder = [9,15,7,20,3]
**Output:** [3,9,20,null,null,15,7]

**Example 2:**

**Input:** inorder = [-1], postorder = [-1]
**Output:** [-1]

**Constraints:**

- `1 <= inorder.length <= 3000`
- `postorder.length == inorder.length`
- `-3000 <= inorder[i], postorder[i] <= 3000`
- `inorder` and `postorder` consist of **unique** values.
- Each value of `postorder` also appears in `inorder`.
- `inorder` is **guaranteed** to be the inorder traversal of the tree.
- `postorder` is **guaranteed** to be the postorder traversal of the tree.



## Explanation & Solution

Inorder traversal of a binary tree means visiting its nodes in the order of "left subtree, root, right subtree". For example, given the binary tree:

markdownCopy code

         3    
        / \
       9   20
          /  \     15   7`

The inorder traversal is: [9, 3, 15, 20, 7]

Postorder traversal of a binary tree means visiting its nodes in the order of "left subtree, right subtree, root". For example, given the binary tree:

markdownCopy code

         3    
        / \
       9   20
          /  \
         15   7`

The postorder traversal is: [9, 15, 7, 20, 3]

The problem is to construct the binary tree from these two traversals. The key observation is that the last element in the postorder traversal is always the root of the current subtree. Using this root element, we can find its index in the inorder traversal, which splits the inorder traversal into the left and right subtrees. Recursively applying this idea, we can construct the binary tree.

The time complexity of the solution we provided is O(n), where n is the number of nodes in the binary tree, because we visit each node exactly once. The space complexity is also O(n), because we use recursion to build the binary tree.
