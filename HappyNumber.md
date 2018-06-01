# easy_1|Happy Number 
##  问题分析
编写一个算法来判断一个数是不是“快乐数”。

一个“快乐数”定义为：对于一个正整数，每一次将该数替换为它每个位置上的数字的平方和，然后重复这个过程直到这个数变为 1，也可能是无限循环但始终变不到 1。如果可以变为 1，那么这个数就是快乐数。
## 代码实现
```cpp
class Solution {
public:
    bool isHappy(int n) {
        if(n == 1)
            return true;  
        if(n <= 0 || n == 4)
            return false;  
        while(n !=1 && n != 4){
            int sum = 0;
            int x;
            while(n != 0){
                x = n % 10;
                n = n / 10;
                sum += x * x;
            }
           n = sum; 
        }
        if(n == 1)
            return true;  
        if(n == 4)
            return false;
    }   
};
```
>## 思路总结
>所有不快乐数的数位平方和计算，最後都会进入 4 → 16 → 37 → 58 → 89 → 145 → 42 → 20 → 4 的循环中，所以只要看结果能得到1还是4，1则是快乐数，4则是不快乐数。
