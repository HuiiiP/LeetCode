# Find the Difference
## 问题分析
给定两个字符串 s 和 t，它们只包含小写字母。
字符串 t 由字符串 s 随机重排，然后在随机位置添加一个字母。
请找出在 t 中被添加的字母
## 代码实现
```cpp
class Solution {
public:
    char findTheDifference(string s, string t) {
    vector<int> count(26, 0);
    for (int i = 0; i < s.length(); i++)
    {
        count[s[i] - 'a']++;
    }
    for (int j = 0; j < t.length(); j++)
    {
        count[t[j] - 'a']--;
    }
    for (int i = 0; i < count.size(); i++)
    {
        if (count[i] == - 1)
            return i + 'a';
    }
    return 'z';  
    }
};
```
>## 思路总结
>利用数组。
