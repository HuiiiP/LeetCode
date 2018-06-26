# Add Strings
## 问题分析
给定两个字符串形式的非负整数 num1 和num2 ，计算它们的和。
注意：
num1 和num2 的长度都小于 5100.
num1 和num2 都只包含数字 0-9.
num1 和num2 都不包含任何前导零。
你不能使用任何內建 BigInteger 库， 也不能直接将输入的字符串转换为整数形式。
## 代码实现
```cpp
class Solution {
public:
    string addStrings(string num1, string num2) {
        string num;
        int l1 = num1.length();
        int l2 = num2.length();
        int carry = 0;
        for(int i = l1 - 1, j = l2 -1; i >= 0 || j >= 0; i--, j--){
            int temp = 0;
            if(i >= 0){
                temp += num1[i] - '0';
            }
            if(j >= 0){
                temp += num2[j] - '0';
            }
            if(carry){
                temp++;
            }
            carry = temp / 10;
            temp %= 10;
            num = char (temp + '0') + num;
        }
        if(carry)
            num = char (carry + '0') + num;
        return num;
    }
};
```
>## 思路总结
>该算法为大数相加使用字符串string实现的问题。首先算出两个字符串的长度，并从两个字符串的最后一个字符开始循环，两个字符串对应位置的值相加，若有进制，则保存。若某一字符串的长度较长，需要将该字符串剩下的字符遍历完成，所以循环退出的条件是i>=0||j>=0；
>这里需要注意的是对字符串位置的操作，需要从两个给定字符串的最后一个位置开始，并且每次得到的结果应放置到结果字符串的首位置。
>对于数字和字符的相互转换，这里需要用到‘0’。
