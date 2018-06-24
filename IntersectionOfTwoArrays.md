# Intersection of Two Arrays
## 问题分析
给定两个数组，写一个函数来计算它们的交集。
例子:
 给定 num1= [1, 2, 2, 1], nums2 = [2, 2], 返回 [2].
提示:
每个在结果中的元素必定是唯一的。
我们可以不考虑输出结果的顺序
## 代码实现
```cpp
class Solution {
public:
    vector<int> intersection(vector<int>& nums1, vector<int>& nums2) { 
            sort(nums1.begin(), nums1.end());
            sort(nums2.begin(), nums2.end());
            vector<int> result;
            int mark;
            for (int i = 0, j = 0; i < nums1.size() && j < nums2.size(); )
            {
                if (nums1[i] < nums2[j])
                    i++;
                else if (nums1[i] > nums2[j])
                    j++;
                else if (nums1[i] == nums2[j])
                {
                    if (result.size() == 0 || nums1[i] != mark)
                    {
                        result.push_back(nums1[i]);
                        mark = nums1[i];
                    }
                    i++;
                    j++;
                }
            } 
            return result;
    }
};
```
>## 思路总结
>1）对数组nums1进行排序；2）对数组nums2进行排序；3）遍历数组nums1和nums2中元素，并比较对应的元素，若相等，则判断其值是否与结果中最后保存的元素是否相等，相等则直接变化两个索引，否则将该值保存到结果中，并变化两个索引
不等，则变化较小元素对应的索引即可
