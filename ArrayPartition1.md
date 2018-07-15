# Array Partition I
## 问题分析
给定长度为 2n 的数组, 你的任务是将这些数分成 n 对, 例如 (a1, b1), (a2, b2), ..., (an, bn) ，使得从1 到 n 的 min(ai, bi) 总和最大。

示例 1:

输入: [1,4,3,2]

输出: 4

解释: n 等于 2, 最大总和为 4 = min(1, 2) + min(3, 4).

提示:

n 是正整数,范围在 [1, 10000].

数组中的元素范围在 [-10000, 10000].
## 代码实现
```cpp
class Solution {
public:
    int arrayPairSum(vector<int>& nums) {
        int res=0;
        sort(nums.begin(),nums.end());
        for(int i=0;i<nums.size();i+=2)
        {
            res+=nums[i];
        }
        return res;
    }
};
```
>## 思路总结
>假设从数列中取出的数为A1-An/2，那么肯定存在一组数B1-Bn/2，不难想象，要使得结果最大，那么Ai的最佳取法即为顺序排列中的奇数位。
