## 题目描述

给定一个double类型的浮点数base和int类型的整数exponent。求base的exponent次方。保证base和exponent不同时为0
***

### 思路

暴力解法时间复杂度为O(n).这里推荐使用二进制的快速幂解法，它的时间复杂度是O（logn).

对底数是否为零和指数的正负进行完整的判断后，用位移运算计算出最后的数值
***

### 题解

```java
public class Solution {
    public double Power(double base, int exponent) {
        double res = 1,curr = base;
            int n;
            if(exponent > 0){
                n = exponent;
            }else if(exponent < 0){
                if(base == )
                    throw new RuntimeException("分母不能为0"); 
                n = -exponent;
            }else{// n == 0 
                return 1;// 0的0次方
            }
            while(n != 0){
                if((n & 1) == 1)
                    res *= curr;
                curr *= curr;// 翻倍
                n >>= 1;// 右移一位
            }
            return exponent >= 0 ? res : (1 / res); 
  }
}
```
