# Hamming Distance 
## 问题分析
两个整数之间的汉明距离指的是这两个数字对应二进制位不同的位置的数目。
给出两个整数 x 和 y，计算它们之间的汉明距离。
注意：
0 ≤ x, y < 2^31.
## 代码实现
```cpp
class Solution {
public:
    int hammingDistance(int x, int y) {
        int dis = 0, z = 0;
        z = x ^ y;
        while(z > 0){
            dis++;
            z = z & (z - 1);
        }
        return dis;
    }
};
```
>## 思路总结
>二进制位不同即是异或运算。得出结果后计算1的个数。
>区别于Number of 1 Bit一题中使用的取余的方法。在这里将z与z-1做与运算，结果也做相同操作，运算几次就有几个1。
