# Distribute Candies
## 问题分析
给定一个偶数长度的数组，其中不同的数字代表着不同种类的糖果，每一个数字代表一个糖果。你需要把这些糖果平均分给一个弟弟和一个妹妹。返回妹妹可以获得的最大糖果的种类数。

示例 1:

输入: candies = [1,1,2,2,3,3]
输出: 3
解析: 一共有三种种类的糖果，每一种都有两个。
     最优分配方案：妹妹获得[1,2,3],弟弟也获得[1,2,3]。这样使妹妹获得糖果的种类数最多。
示例 2 :

输入: candies = [1,1,2,3]
输出: 2
解析: 妹妹获得糖果[2,3],弟弟获得糖果[1,1]，妹妹有两种不同的糖果，弟弟只有一种。这样使得妹妹可以获得的糖果种类数最多。
## 代码实现
```cpp
class Solution {
public:
    int distributeCandies(vector<int>& candies) {
        if(candies.size()<1)
			return 0;
		bool kinds[200005] = {0};
		int kindnum = 0;
		for(int i = 0; i<candies.size(); i++){
			int idx = candies[i] + 100000;
			if(!kinds[idx]){
				kinds[idx] = 1;
				kindnum ++;
			}
		}
		if(kindnum >= candies.size()/2)
			return candies.size()/2;
		return kindnum;
    }
};
```
>## 思路总结
>1M的内存空间可以支持32位int型数组大小为26万+，所以可以使用int或bool型数组对所有第一次出现的candy种类进行记录，并使用kindnum变量记录不同candy种类数，如果出现过则不修改kindnum。最终根据kindnum大小进行返回操作，若kindnum大于candies长度一半，则sister最多获得candies.size()/2种糖果；若小于，则返回kindnum
