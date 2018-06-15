# Jewels and Stones
## 问题分析
 给定字符串J 代表石头中宝石的类型，和字符串 S代表你拥有的石头。 S 中每个字符代表了一种你拥有的石头的类型，你想知道你拥有的石头中有多少是宝石。

J 中的字母不重复，J 和 S中的所有字符都是字母。字母区分大小写，因此"a"和"A"是不同类型的石头。
## 代码实现
```cpp
class Solution {
public:
    int numJewelsInStones(string J, string S) {
        int ns = S.length();
        int nj = J.length();
        int sum = 0;
        for(int i = 0; i < ns; i++){
            for(int j = 0; j < nj; j++){
                if(S[i] == J[j])
                    sum++;
            }
        }
        return sum;
    }
};
```
>## 思路总结
>通过遍历字符串S和J，两两进行比较，判断stone中有多少颗jewel。
