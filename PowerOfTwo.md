# Power of Two
## 问题分析
给定一个整数，写一个函数来判断它是否是 2 的幂次方。
## 代码实现
```cpp
class Solution {
public:
    bool isPowerOfTwo(int n) {
        int c = n & (n - 1);
        if( c == 0 && n > 0)
            return true;
        else
            return false;
    }
};
```
>## 思路总结
>2的N次幂特点：仅由首位为1，其余各位都为0。所以n与(n-1)的结果一定是0。
