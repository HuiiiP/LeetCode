# easy_11|Valid Perfect Square
## 问题分析
给定一个正整数 num，编写一个函数，如果 num 是一个完全平方数，则返回 True，否则返回 False。
注意：不要使用任何内置的库函数，如  sqrt。
## 代码实现
```cpp
class Solution {
public:
    bool isPerfectSquare(int num) {
        int i = 1;
     while (num > 0) {
         num -= i;
         i += 2;
     }
     return num == 0;
    }
};
```
>## 思路总结
>通过数学方法：等差数列，1+3+5+……+2n-1（一共n个数）=n^2。
