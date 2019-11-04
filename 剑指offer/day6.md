## 题目描述

输入一个链表，反转链表后，输出新链表的表头。

***

## 思路

定义两个空节点，一个pre指向head作为反转链表的表尾，另一个next用于存储head下一节点的内容，否则当head重新指向pre时链表断掉。然后pre和head依次前进一个节点（继续下一次的指针反转）。当head为null时，pre就是最后一个节点，此时链表反转已经完成。

***

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
        public ListNode ReverseList(ListNode head) {
            ListNode pre = null;
            ListNode next = null;
            while(head != null) {
                next = head.next;
                head.next = pre;
                pre = head;
                head = next;
            }
            return pre;
        }
    }
```