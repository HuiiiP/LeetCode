# Reverse Integer
## 问题分析
给定一个 32 位有符号整数，将整数中的数字进行反转。
## 代码实现
```cpp
class Solution {
public:
    int reverse(int x) {
        int num;
        long long int sum = 0;
        while(x != 0){
            num = x % 10;
            sum = sum * 10 + num;
            x /= 10;
        }
        if(sum > INT_MAX || sum < INT_MIN)
            return 0;
        else
            return sum;
    }
};
```
>## 思路总结
>有两点要注意：
>1、INT_MAX 和 INT_MIN 来表示int型所表示的最大和最小。
>2、先用long long int 型来保存数据，然后再进行int型的溢出判断。
