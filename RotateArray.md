# Rotate Array
## 问题分析
给定一个数组，将数组中的元素向右移动 k 个位置，其中 k 是非负数。
示例 1:
输入: [1,2,3,4,5,6,7] 和 k = 3
输出: [5,6,7,1,2,3,4]
解释:
向右旋转 1 步: [7,1,2,3,4,5,6]
向右旋转 2 步: [6,7,1,2,3,4,5]
向右旋转 3 步: [5,6,7,1,2,3,4]
示例 2:
输入: [-1,-100,3,99] 和 k = 2
输出: [3,99,-1,-100]
解释: 
向右旋转 1 步: [99,-1,-100,3]
向右旋转 2 步: [3,99,-1,-100]
## 代码实现
```cpp
class Solution {
public:
    void swapVector(vector<int> &nums,int first,int last)
    {
        for(int i=first, j=last; i<j; i++, j--)
        {
            swap(nums[i],nums[j]);
        }
    }
    void rotate(vector<int>& nums, int k) {
        int length = nums.size();
        k = k % length;
        swapVector(nums, 0, length-k-1);
        swapVector(nums, length-k, length-1);
        swapVector(nums, 0, length-1);
    }
};
```
>## 思路总结
>该题思路为3步：利用k将数组分为两半，翻转左右两边的数组，翻转总数组。
1 2 3 4 5 6 7　　如果k = 3 的话， 会变成 5 6 7 1 2 3 4
1 2 3 4 | 5 6 7　　middle = 7 - 3 = 4，分为左边4个数字，右边3个数字
4 3 2 1 | 7 6 5　　分别把左右reverse 一下
5 6 7 | 1 2 3 4　　把总数组reverse 一下就会得到答案
