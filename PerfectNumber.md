# Perfect Number
## 问题分析
对于一个 正整数，如果它和除了它自身以外的所有正因子之和相等，我们称它为“完美数”。
给定一个 正整数 n， 如果他是完美数，返回 True，否则返回 False
## 代码实现
```cpp
class Solution {
public:
    bool checkPerfectNumber(int num) {
      if(num == 1) return false;  
      int n = sqrt(num);  
      int ans = 1;  
      for(int i = 2;i <= n;i++){  
          if(num % i == 0){  
              ans += i + num / i;  
          }  
      }  
      return ans == num;   
    }
};
```
>## 思路总结
>该题按题目计算即可，只是注意不要忘记1的话要返回false。
