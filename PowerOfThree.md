# Power of Three
## 问题分析
给定一个整数，写一个函数来判断它是否是 3 的幂次方。
## 代码实现
```cpp
class Solution {
public:
    bool isPowerOfThree(int n) {
        double a = log10(n) / log10(3);
        if (a - (int)(a) == 0)
            return true;
        else
            return false;
    }
};
```
>## 思路总结
>计算输入值以3为底的对数，如果得到的是整数，即为3的幂次方。
