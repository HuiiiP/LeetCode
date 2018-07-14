# Climbing Stairs
## 问题分析
假设你正在爬楼梯。需要 n 步你才能到达楼顶。

每次你可以爬 1 或 2 个台阶。你有多少种不同的方法可以爬到楼顶呢？

注意：给定 n 是一个正整数。

示例 1：

输入： 2

输出： 2

解释： 有两种方法可以爬到楼顶。

1.  1 步 + 1 步

2.  2 步

示例 2：

输入： 3

输出： 3

解释： 有三种方法可以爬到楼顶。

1.  1 步 + 1 步 + 1 步

2.  1 步 + 2 步

3.  2 步 + 1 步
## 代码实现
```cpp
class Solution {
public:
    int climbStairs(int n) {
        if(n <= 2)
            return n;
        else{
            int p = 1;
            int q = 2;
            for(int i = 0; i < n - 2; i++){
                int t = p + q;
                p = q;
                q = t;
            }
            return q;
        }
    }
};
```
>## 思路总结
>判断n需要多少步时只需要将n-1的步数及n-2的步数相加即可。
