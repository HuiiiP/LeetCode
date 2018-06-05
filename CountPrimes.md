# Count Primes
## 问题分析
统计所有小于非负整数 n 的质数的数量。
## 代码实现
```cpp
class Solution {
public:
    int countPrimes(int n) {
        bool jud[10000000];
        jud[2] = false;
        for(int i = 3; i < n; i++){
            if(i %2 == 0){
                jud[i] = true;
            }
            else{
                jud[i] = false;
            }
        }
        for(int i = 3; i < n; i++){
            if(!jud[i]){
                if(i * i > n)
                    break;
                else{
                    for(int j = 2; i * j < n; j++){
                        jud[i *j] = true;
                    }
                }
            }
        }
        int count = 0;
        for(int i = 2; i < n; i++){
            if(!jud[i]){
                count++;
            }
        }
        return count;
    }
};
```
>## 思路总结
>厄拉多塞筛法(Sieve of Eeatosthese)：先将 2~n 的各个数放入表中，然后在2的上面画一个圆圈，然后划去2的其他倍数；第一个既未画圈又没有被划去的数是3，将它画圈，再划去3的其他倍数；现在既未画圈又没有被划去的第一个数 是5，将它画圈，并划去5的其他倍数……依次类推，一直到所有小于或等于 n 的各数都画了圈或划去为止。这时，表中画了圈的以及未划去的那些数正好就是小于 n 的素数。
![Alt text](./Sieve_of_Eratosthenes_animation.gif)
![enter image description here](http://upload.wikimedia.org/wikipedia/commons/b/b9/Sieve_of_Eratosthenes_animation.gif)
