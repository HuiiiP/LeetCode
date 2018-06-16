# Nth Digit
## 问题分析
在无限的整数序列 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, ...中找到第 n 个数字。
## 代码实现
```cpp
class Solution {
public:
    int findNthDigit(int n) {
        long digit = 1, ith = 1, base = 9;  
        while(n > base*digit)  
        {  
            n -= base*(digit++);  
            ith += base;  
            base *= 10;  
        }  
        return to_string(ith+(n-1)/digit)[(n-1)%digit]-'0';  
    }
};
```
>## 思路总结
>可以分三步来做：１．找出给定的n落在几位数的范围内２．找到具体落在哪个数字３．找出具体在哪一位上
