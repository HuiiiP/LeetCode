# Third Maximum Number
## 问题分析
给定一个非空数组，返回此数组中第三大的数。如果不存在，则返回数组中最大的数。要求算法时间复杂度必须是O(n)。
## 代码实现
```cpp
class Solution {
public:
    int thirdMax(vector<int>& nums) {
        long Max = LONG_MIN, secMax = LONG_MIN, thirdMax = LONG_MIN;
        for(auto num: nums)
        {
            if(num > Max)
            {
                if(secMax!=LONG_MIN) thirdMax = secMax;
                if(Max!=LONG_MIN) secMax = Max;
                Max = num;
            }
            else if(num > secMax && num!= Max)
            {
                if(secMax!=LONG_MIN) thirdMax = secMax;
                secMax = num;
            }
            else if(num > thirdMax && num!= Max && num!=secMax) thirdMax = num;
        }
        return thirdMax==LONG_MIN?Max:thirdMax;
    }
};
```
>## 思路总结
>保存三个变量代表最大的三个数，并且三个数必须是不同的．
>每次先更新最大的数，如果可以更新，还要看是否能进行转移，也就是原来最大的数变为第二大的数，原来第二大的数变为第三大的数．
>然后在比较如果当前数比最大数小是否比第二大的数大．
>如果最后没有第三大的数就返回最大的数
