## 题目描述

操作给定的二叉树，将其变换为源二叉树的镜像。

***

## 思路

暴力 + 递归

***

## 题解

```java
    /**
    public class TreeNode {
        int val = 0;
        TreeNode left = null;
        TreeNode right = null;

        public TreeNode(int val) {
            this.val = val;

        }

    }
    */
    public class Solution {
        public void Mirror(TreeNode root) {
            TreeNode tmp = null;
            if(root != null) {
                tmp = root.left;
                root.left = root.right;
                root.right = tmp;
                if(root.left != null) {
                    Mirror(root.left);
                }
                if(root.right != null) {
                    Mirror(root.right);
                }
            }
        }
    }
```