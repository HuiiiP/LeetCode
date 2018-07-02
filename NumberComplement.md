# Number Complement
## 问题分析
给定一个正整数，输出它的补数。补数是对该数的二进制表示取反。
注意:
给定的整数保证在32位带符号整数的范围内。
你可以假定二进制数不包含前导零位。
## 代码实现
```cpp
class Solution {
public:
    int findComplement(int num) {
        int tem = 1, temp = num;
        while(temp > 0){
            tem = tem << 1;
            temp = temp >> 1;
        }
        return num ^ (tem - 1);
    }
};
```
>## 思路总结
>1.先确定转化为二进制之后的数字位数
>2.再取对应的数量的1，二者异或运算，得到所求的数字。
