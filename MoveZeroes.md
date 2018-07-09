# Move Zeroes
## 问题分析
给定一个数组 nums，编写一个函数将所有 0 移动到数组的末尾，同时保持非零元素的相对顺序。
## 代码实现
```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        vector<int> num1(nums);
        nums.clear();
        int i;
        int count =0;
        for(i=0;i<num1.size();i++)
        {
            if(num1[i]==0)
            {
                count++;
                continue;
            }
            else
            {
                nums.push_back(num1[i]);
            }
        }
        for(i=0;i<count;i++)
        {
            nums.push_back(0);
        }
    }
};
```
>## 思路总结
>一层循环发现为0的元素，则将count自增，count变量用来统计数组（顺序容器）中0的个数。发现不为0的元素就将其插入尾部。最后，在尾部插入count数个元素0。
