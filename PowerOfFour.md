# Power of Four
## 问题分析
给定一个整数 (32位有符整数型)，请写出一个函数来检验它是否是4的幂。
## 代码实现
```cpp
class Solution {
public:
    bool isPowerOfFour(int num) {
    if(num<=0)  
        return false;  
    return (num & num-1)==0 && (num&0x55555555)==num; 
    }
};
```
>## 思路总结
>4的N次幂特点：只能是奇数位为1。
>所以先判断是否为2的幂，然后通过与0X55555555(....1010101)进行与操作，保留奇数位，判断是否改变。
