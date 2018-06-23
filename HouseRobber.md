# House Robber
## 问题分析
你是一个专业的小偷，计划偷窃沿街的房屋。每间房内都藏有一定的现金，影响你偷窃的唯一制约因素就是相邻的房屋装有相互连通的防盗系统，如果两间相邻的房屋在同一晚上被小偷闯入，系统会自动报警。
给定一个代表每个房屋存放金额的非负整数数组，计算你在不触动警报装置的情况下，能够偷窃到的最高金额。
## 代码实现
```cpp
class Solution {
public:
    int rob(vector<int>& nums) {
        int n = nums.size();
        if(n == 0)
            return 0;
        else if(n == 1)
            return nums[0];
        else
        {
            vector<int> maxV(n, 0);
            maxV[0] = nums[0];
            maxV[1] = max(nums[0], nums[1]);
            for(int i = 2; i < n; i ++)
                maxV[i] = max(maxV[i-2]+nums[i], maxV[i-1]);
            return maxV[n-1];
        }
    }
};
```
>## 思路总结
>通俗点理解，本题其实就是：给定一个整数数组，求解数组中连续的不相邻元素的和的最大值。例如：对于数组中的元素A1,A2,A3,A4，则需要判断A1+A3,A1+A4,A2+A4中的最大值即为所求。
