# Fizz Buzz
## 问题分析
写一个程序，输出从 1 到 n 数字的字符串表示。
1. 如果 n 是3的倍数，输出“Fizz”；
2. 如果 n 是5的倍数，输出“Buzz”；
3.如果 n 同时是3和5的倍数，输出 “FizzBuzz”。
## 代码实现
```cpp
class Solution {
public:
    vector<string> fizzBuzz(int n) {
        vector<string> s;
        for(int i=1; i<=n; i++){
            if(i % 15 == 0)
                s.push_back("FizzBuzz");
            else if(i % 3 == 0)
                s.push_back("Fizz");
            else if(i % 5 == 0)
                s.push_back("Buzz");
            else
                s.push_back(to_string(i));
        }
        return s;
    }
};
```
>## 思路总结
>该题只要注意如何将int类型数值转为string类型的字符。在这里使用了to_string()来实现。
