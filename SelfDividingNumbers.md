# SelfDividingNumbers
## 问题分析
自除数 是指可以被它包含的每一位数除尽的数。
例如，128 是一个自除数，因为 128 % 1 == 0，128 % 2 == 0，128 % 8 == 0。
还有，自除数不允许包含 0 。
给定上边界和下边界数字，输出一个列表，列表的元素是边界（含边界）内所有的自除数。
## 代码实现
```cpp
class Solution {
public:
   bool judge(int n){
        int t = n;
        while(t > 0){
            if(t % 10 == 0)
                break;
            if(n % (t % 10) != 0)
                break;
            t /= 10;
        }
        return t==0;
    }
    vector<int> selfDividingNumbers(int left, int right) {
        vector<int> sd;
        for(int i = left; i <= right; i++){
            if(judge(i))
                sd.push_back(i);
        }
        return sd;
    }
};
```
>## 思路总结
>用了一个函数实现了连除和判断的过程：逐位判断是否能除尽。
