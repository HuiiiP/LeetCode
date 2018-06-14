# Judge Route Circle
## 问题分析
初始位置 (0, 0) 处有一个机器人。给出它的一系列动作，判断这个机器人的移动路线是否形成一个圆圈，换言之就是判断它是否会移回到原来的位置。

移动顺序由一个字符串表示。每一个动作都是由一个字符来表示的。机器人有效的动作有 R（右），L（左），U（上）和 D（下）。输出应为 true 或 false，表示机器人移动路线是否成圈。
## 代码实现
```cpp
class Solution {
public:
    bool judgeCircle(string moves) {
        if(moves.length() == 0) return true;  
        if(moves.length() %2 != 0) return false;  
        int x = 0;
        int y = 0;  
        for(int i = 0; i < moves.length(); i ++) {  
            if(moves[i] == 'U') y++;  
            else if(moves[i] == 'D') y--;  
            else if(moves[i] == 'R') x++;  
            else if(moves[i] == 'L') x--;  
        }    
        if(x == 0 && y == 0)  
            return true;  
        else
            return false; 
    }
};
```
>## 思路总结
>要注意两点：
>1、字符串求长度str.length()的用法。
>2、输入string类型的字符串a后，a[0]、a[1]就是第一个和第二个字符。
