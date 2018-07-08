# Plus One
## 问题分析
给定一个非负整数组成的非空数组，在该数的基础上加一，返回一个新的数组。
最高位数字存放在数组的首位， 数组中每个元素只存储一个数字。
你可以假设除了整数 0 之外，这个整数不会以零开头。
## 代码实现
```cpp
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        int c = 1;
        for(int i = digits.size() - 1; i >= 0; i--){
            int a = digits[i] + c;
            digits[i] = a % 10;
            c = a / 10;
        }
        if(c == 1)
            digits.insert(digits.begin(), 1);
        return digits;
    }
};
```
>## 思路总结
>令进位标识初始值为1,不断处理进位,如果最后还有进位，则在数组最前面在插入1.
