# Sum of Square Numbers
## 问题分析
给定一个非负整数 c ，你要判断是否存在两个整数 a 和 b，使得 a2 + b2 = c。
## 代码实现
```cpp
class Solution {
public:
    bool judgeSquareSum(int c) {
        bool flag = false;
        if(c == 0)
            flag = true;
        for(int i = 0; i < sqrt(c); i++){
            double temp = sqrt(c - i * i);
            if(temp == (int)temp)
                flag = true;
        }
        return flag;
    }
};
```
>## 思路总结
>遍历[0,sqrt(c)]，枚举c-i*i，并判断其是否为完全平方数。
>要注意题中0的返回值为true。
