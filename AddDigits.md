# Add Digits
## 问题分析
给定一个非负整数 num，反复将各个位上的数字相加，直到结果为一位数。
## 代码实现
```cpp
class Solution {
public:
    int addDigits(int num) {
        if (num < 10)
            return num;
        int sum = 0;
        while(num > 0){
            sum += num % 10;
            num /= 10;
        }
        return addDigits(sum);
    }
};
```
>## 思路总结
>使用递归
