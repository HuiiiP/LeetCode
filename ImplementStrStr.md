# Implement strStr()
## 问题分析
实现 strStr() 函数。
给定一个 haystack 字符串和一个 needle 字符串，在 haystack 字符串中找出 needle 字符串出现的第一个位置 (从0开始)。如果不存在，则返回  -1。
## 代码实现
```cpp
class Solution {
public:
    int strStr(string haystack, string needle) {
		if (haystack.empty() && needle.empty())
			return 0;
		if (needle.size() == 0)
			return 0;
		if (needle.size() > haystack.size())
			return -1;
		else
			return kmp(haystack, needle);
	}
	//求子字符串的K值
	vector<int> getNext(string tmp) {
		int i = tmp.size();
		int j = 0;
		int k = -1;
		vector<int> ans(i);
		ans[0] = -1;
		while (j < i - 1)
		{
			if (k == -1 || tmp[j] == tmp[k]) {
				k++;
				j++;
				ans[j] = k;
			}
			else
				k = ans[k];
		}
		return ans;
	}
	int kmp(string s, string sub) {
		int i = 0;
		vector<int> next = getNext(sub);
		int j = 0;
		while (i < s.size())
		{
			if (j == -1 || s[i] == sub[j]) {
				i++;
				j++;
			}
			else
				j = next[j];
			if (j == sub.size())
				return i - j;
		}
		return -1;
	}
};
```
>## 思路总结
>https://blog.csdn.net/qq_14821023/article/details/50813095
>借鉴了该篇的思路和算法。
