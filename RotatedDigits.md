# Rotated Digits
## 问题分析
我们称一个数 X 为好数, 如果它的每位数字逐个地被旋转 180 度后，我们仍可以得到一个有效的，且和 X 不同的数。要求每位数字都要被旋转。
如果一个数的每位数字被旋转以后仍然还是一个数字， 则这个数是有效的。0, 1, 和 8 被旋转后仍然是它们自己；2 和 5 可以互相旋转成对方；6 和 9 同理，除了这些以外其他的数字旋转以后都不再是有效的数字。
现在我们有一个正整数 N, 计算从 1 到 N 中有多少个数 X 是好数？
## 代码实现
```cpp
class Solution {
public:
    int rotatedDigits(int N) {
        int sum = 0;
        for(int i = 1; i <= N; i++){
            if(isValid(i))
                sum++;
        }
        return sum;
    }
    
    bool isValid(int n){
        bool flag = false;
        while(n > 0){
            switch(n % 10){
                case 3: return false; break;
                case 4: return false; break;
                case 7: return false; break;
                case 0: break;
                case 1: break;
                case 8: break;
                default: flag = true;
            }
            n /= 10;
        }
        return flag;
    }
};
```
>## 思路总结
>遍历[1,N]，查看每一个数是否符合。（因为N最大值为10000，所以暴力求解法可用）
