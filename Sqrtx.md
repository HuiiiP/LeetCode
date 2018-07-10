# Sqrt(x)
## 问题分析
实现 int sqrt(int x) 函数。
计算并返回 x 的平方根，其中 x 是非负整数。
由于返回类型是整数，结果只保留整数的部分，小数部分将被舍去。
## 代码实现
```cpp
class Solution {
public:
    int mySqrt(int x) {
        double begin = 0;
        double end = x;
        double result = 1;
        double mid = 1;
        while(abs(result-x) > 0.000001){
            mid = (begin+end)/2;
            result = mid*mid;
            if(result > x)   
                end = mid;
            else begin = mid;
        }
        return (int)mid;
    }
};
```
>## 思路总结
>二分法
