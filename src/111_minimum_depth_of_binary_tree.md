## Minimum Depth of Binary Tree

## Description

```Python
Given a binary tree, find its minimum depth.

The minimum depth is the number of nodes along the shortest path from the root node down to the nearest leaf node.

Note: A leaf is a node with no children.

Example:

Given binary tree [3,9,20,null,null,15,7],

    3
   / \
  9  20
    /  \
   15   7
return its minimum depth = 2.
```

### Python Solutions

#### Approach : Recursive

* Time complexity : O(n)
* Space complexity : O(n)


```Python
class Solution(object):
    def min_depth(self, root):
        """
        Given a binary tree, find its minimum depth

        Args:
            root(TreeNode): The root of tree
        
        Returns:
            The minimum depth of the tree(int)
        """
        if root is None:
            return 0
        elif root.left is not None and root.right is not None:
            return 1 + min(self.minDepth(root.left), self.minDepth(root.right))
        elif root.left is not None:
            return 1 + self.minDepth(root.left)
        elif root.right is not None:
            return 1 + self.minDepth(root.right)
        else:
            return 1
```

