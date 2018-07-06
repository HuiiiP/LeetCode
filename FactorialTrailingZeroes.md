# Factorial Trailing Zeroes
## 问题分析
给定一个整数 n，返回 n! 结果尾数中零的数量。
## 代码实现
```cpp
class Solution {
public:
    int trailingZeroes(int n) {
        int ans = 0;
        while(n) {
            n /= 5;
            ans += n;
        }
        return ans;
    }
};
```
>## 思路总结
>所有5的倍数会添加一个0，所有5^2的倍数会比5的倍数多添加一个0。
