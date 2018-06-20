# Palindrome Number
## 问题分析
判断一个整数是否是回文数。回文数是指正序（从左向右）和倒序（从右向左）读都是一样的整数。
## 代码实现
```cpp
class Solution {
public:
    bool isPalindrome(int x) {
        int r;
        int a = 0;
        if(x < 0 || (x != 0 && x % 10 ==0))
            return false;
        while(x >a){
            r = x % 10;
            x /= 10;
            a = a * 10 + r;
        }
        if(x == a || a / 10 == x)
            return true;
        else
            return false;
    }
};
```
>## 思路总结
>采用判断前后一半数字，判断条件就是反转后的数大于原数，这就涉及数字个数是偶数还是奇数，偶数判断是否相等，奇数先除十在判断，注意细节的是尾数为零的不是回文数，但零是回文数
