---
title: "The constant space tree traversal algorithm: Morris Traversal"
date: 2019-07-27T21:39:00+04:00
draft: false
tags: ["algorithm", "tree", "traversal"]
slug: "morris-traversal"
---

## What is Morris Traversal?

Morris Traversal is an algorithm that allows us to traverse the tree without using a stack or recursion.
That means we can traverse the tree with O(n) time complexity and O(1) space complexity.
The usual method of using stack or recursion to traverse the tree would require O(h) space,
with h being the height of the tree, with worst case space complexity of O(n).

Basically Morris Traversal makes sense if we have a fat tree and we want to be economical on space usage.


## How does it work?

The essence of the algorithm is to build a bridge between the root, and its predecessor in its left subtree
for the first time, and then remove this bridge when we traverse to the predecessor for the second time.

The pseudo code for inorder traversal is as follows:

```
1. Initialize current as root 
2. While current is not NULL
   If the current does not have left child
      a) Visit current node
      b) Go to the right, i.e., current = current->right
   Else
      a) predecessor = findPredecessor(current), aka
		 traverse to the rightmost on left subtree
      b) If predecessor.right does not exist
		  First make current as the right child of the predecessor
		  (build the bridge)
		  Then go to left child, current = current.left
      c) If predecessor.right is current
		  First remove the bridge: predecessor.right = null
		  Visit current node
		  Then go to right child, current = current.right
```
{{< figure src="/images/morris-traversal.jpg" >}}

 
### Java implementation
``` java
public class MorrisTraversal(Node root) {
	public void inorder(Node root) {
		while(root != null) {
			if(current.left == null) {
				System.out.println(current.data + " ");
				current = current.right;
			} else {
				Node predecessor = root.left;
				while(predecessor.right != current && predecessor.right != null) {
					predecessor = predecessor.right;
				}
				if(predecessor.right == null) {
					predecessor.right = current;
					current = current.left;
				} else {
					predecessor.right = null;
					System.out.println(current.data + " ");
					current = current.right;
				}
			}
		}	
	}
}
```
