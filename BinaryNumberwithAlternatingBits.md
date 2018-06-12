# Binary Number with Alternating Bits
## 问题分析
给定一个正整数，检查他是否为交替位二进制数：换句话说，就是他的二进制数相邻的两个位数永不相等。
## 代码实现
```cpp
class Solution {
public:
    bool hasAlternatingBits(int n) {
        return (((n >> 1) + n) & ((n >> 1) + n +1)) == 0;
    }
};
```
>## 思路总结
>右移一位，判断形如111111这样的数的特性。 即111与1000结果一定为0
