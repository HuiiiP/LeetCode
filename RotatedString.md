# Rotated String
## 问题分析
给定两个字符串, A 和 B。
A 的旋转操作就是将 A 最左边的字符移动到最右边。 例如, 若 A = 'abcde'，在移动一次之后结果就是'bcdea' 。如果在若干次旋转操作之后，A 能变成B，那么返回True。
## 代码实现
```cpp
class Solution {
public:
    bool rotateString(string A, string B) {
        if(A.length() != B.length())
            return false;
        if(A.length() == 0 && B.length() == 0)
            return true;
        else{
            string str = A + A;
            for(int i = 0; i < B.length(); i++){
                int j = 0;
                if(str[i] == B[j]){
                    while(j < B.length()){
                        if(str[i+j] == B[j])
                            j++;
                        else
                            break;
                    }
                    if(j == B.length())
                        return true;
                }
            }
            return false;
        }
    }
};
```
>## 思路总结
>构造str=A+A，看B是否完全在str中即可。
>要特别注意两个边界条件：一是两个字符串长度不等时返回false。二是两个字符串皆为空字符串时返回true。
