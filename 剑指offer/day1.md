##题目描述
我们可以用2*1的小矩形横着或者竖着去覆盖更大的矩形。请问用n个2*1的小矩形无重叠地覆盖一个2*n的大矩形，总共有多少种方法？
***
思路：
    与青蛙上台阶类似。
    在2*n的矩形内放置第一块小矩形时分为两种情况：
    1. 横放 2*1
        -那么余下的空间就有f(n-1)种摆法；
    2. 竖放 1*2
        -那么余下的空间就有f(n-2)种摆法；
    因此总摆法数即为f(n-1) + f(n-2)
***
题解：
    <
        public class Solution {
            public int RectCover(int target) {
                if(target<=0){
                    return 0;
                }
                if(target==1){
                    return 1;
                }
                if(target==2){
                    return 2;
                }else{
                    return RectCover(target-1)+RectCover(target-2);
                }
            }
        }
    >