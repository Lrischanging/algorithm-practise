## 题目描述

输入一个链表，输出该链表中倒数第k个结点。

## 思路

首先定义两个指向头节点的指针f， e。先让e指向第k个节点，然后两个指针同时向后移动，当e到达表尾时，指针f指向的即是倒数第k个节点。

## 题解

```java
    /*
    public class ListNode {
        int val;
        ListNode next = null;

        ListNode(int val) {
            this.val = val;
        }
    }*/
    public class Solution {
        public ListNode FindKthToTail(ListNode head,int k) {
            ListNode f, e;
            f = e = head;
            int i = 0;
            for(; e != null; i++) {
                if(i >= k) {
                    f = f.next;
                }
                e = e.next;
            }
            return i < k ? null : f;
        }
    }
```