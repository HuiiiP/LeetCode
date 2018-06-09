# Base7
## 问题分析
给定一个整数，将其转化为7进制，并以字符串形式输出。
## 代码实现
```cpp
class Solution {
public:
    string convertToBase7(int num) {
        if(num == 0)
            return "0";
        bool flag = (num > 0) ? true : false;
        if(num < 0)
            num = num * (-1);
        string res;
        int tmpe;
        while(num != 0){
            tmpe = num % 7;
            num /= 7;
            res = to_string(tmpe) + res;  //将数值转化为字符串
        }
        if(!flag)
            res = string(1,'-') + res;
        return res;
    }
};
```
>## 思路总结
>该题需要注意：
>1、使用布尔标识符来标志整数是否为负数。
>2、进制转化即是模运算和除运算的结合。
>3、如何将数值转化为字符串、如何连接字符串。
