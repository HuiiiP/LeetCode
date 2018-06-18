# Count and Say
## 问题分析
报数序列是指一个整数序列，按照其中的整数的顺序进行报数，得到下一个数。其前五项如下：
1.     1
2.     11
3.     21
4.     1211
5.     111221
1 被读作  "one 1"  ("一个一") , 即 11。
11 被读作 "two 1s" ("两个一"）, 即 21。
21 被读作 "one 2",  "one 1" （"一个二" ,  "一个一") , 即 1211。
给定一个正整数 n ，输出报数序列的第 n 项。
注意：整数顺序将表示为一个字符串。
## 代码实现
```cpp
class Solution {
public:
    string countAndSay(int n) {
       if(n==0) return "";
    string str="1" ;//开始报数为1
    for(int i=1;i<n;i++)
    {
        string temp;//用于表征几个重复的数字个数 
        int count=1; //用于计算有几个重复的
        for(int j=0;j<str.length();j++)
        {
            if(str[j]==str[j+1])
               count++;
            else
            {
                temp+=('0'+count);
                temp+=str[j];//表示出几个几 
                count=1;                
            } 
        }
        str=temp;        
    }  
    return str;   
    }
};
```
>## 思路总结
>该题目有两个要点：计算重复数有几个和表征重复数的个数。且要注意开始报数时为1。
