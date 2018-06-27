# Add Strings
## 问题分析
给定一个包含 0, 1, 2, ..., n 中 n 个数的序列，找出 0 .. n 中没有出现在序列中的那个数。
## 代码实现
```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        if (nums.empty())
            return 0;
        int n = nums.size();
        int sum = n*(n+1)/2;
        int real_sum = 0;
        for(int i = 0; i < n; i++) {
            real_sum += nums[i];
        }
        return sum - real_sum;
    }
};
```
>## 思路总结
>求出从0~n的累加和，减去数组整体的和，那么由于数组内每个数字不相同，其差就是缺少的那个数字
