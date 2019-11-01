## 题目描述

输入一个整数数组，实现一个函数来调整该数组中数字的顺序，使得所有的奇数位于数组的前半部分，所有的偶数位于数组的后半部分，并保证奇数和奇数，偶数和偶数之间的相对位置不变。
***

### 思路

1. 要想保证原有次序，则只能顺次移动或相邻交换。
2. i从左向右遍历，找到第一个偶数。
3. j从i+1开始向后找，直到找到第一个奇数。
4. 将[i,...,j-1]的元素整体后移一位，最后将找到的奇数放入i位置，然后i++。
5. 終止條件：j向後遍歷查找失敗。
***

### 题解

```java
    public class Solution {
        public void reOrderArray(int [] array) {
            if(array.length == 0 || array.length == 1) {
                return;
            }
            int i = 0, j = 0;
            while(i < array.length) {
                while(array[i] % 2 != 0) {
                    i++;
                }
                j = i + 1;
                while(j < array.length && (array[j] % 2 == 0)) {
                    j++;
                }
                if(j < array.length) {
                    int tmp = array[j];
                    for(int q = j - 1; q >= i; q--) {
                        array[q + 1] = array[q];
                    }
                    array[i] = tmp;
                }else {
                    break;
                }
            }
        }
    }
```