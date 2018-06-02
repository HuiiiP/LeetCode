# Number of 1 Bits    
## 问题分析
编写一个函数，输入是一个无符号整数，返回其二进制表达式中数字位数为 ‘1’ 的个数（也被称为汉明重量）。
## 代码实现
```cpp
class Solution {
public:
    int hammingWeight(uint32_t n) {
        int num = 0;
        while(n > 0){
            num += (n % 2);
            n = n / 2;
        }
        return num;
    }
};
```
>## 思路总结
>二进制表达式中数字位数为“1”，也就是模2所得的余数。
