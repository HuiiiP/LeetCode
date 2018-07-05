# Majority Element
## 问题分析
给定一个大小为 n 的数组，找到其中的众数。众数是指在数组中出现次数大于 ⌊ n/2 ⌋ 的元素。
你可以假设数组是非空的，并且给定的数组总是存在众数。
## 代码实现
```cpp
class Solution {
public:
    int majorityElement(vector<int>& nums) {
        int temp = 0;
        int count = 0;
        for(int i = 0; i < nums.size(); i++){
            if(count == 0){
                temp = nums[i];
                count = 1;
            }
            else{
                if(temp == nums[i])
                    count++;
                else
                    count--;
            }
        }
        return temp;
    }
};
```
>## 思路总结
>每找出两个不同的数，就成对删除即count--，最终剩下的就是所求的。
