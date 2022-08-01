# 242. Valid Anagram
[leetcode 242. Valid Anagram](https://leetcode.com/problems/valid-anagram/)
Given two strings `s` and `t`,return `true` if `t` is an anagram of `s`,and `false` otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

Example 1:
```
Input: s = "anagram", t = "nagaram"
Output: true
```
Example 2:
```
Input: s = "rat", t = "car"
Output: false
```


# Code
python:
```python
# Python collections.Counter，
# 最主要的作用就是計算“可迭代序列中”各個元素（element）的數量
class Solution(object):
    def isAnagram(self, s, t):
        return collections.Counter(s) == collections.Counter(t)
```

C++:
###### Hash Table
```C++
// 在容器中搜索鍵為k的元素並返回找到的元素數。
// 因為unordered_map容器不允許重複鍵，這意味著如果容器中存在具有該鍵的元素，
// 則該函數實際上返回1 ，否則返回 0。
class Solution {
public:
    bool isAnagram(string s, string t) {
        if (s.length() != t.length()) return false;
        int n = s.length();
        unordered_map<char, int> counts;
        for (int i = 0; i < n; i++) {w
            counts[s[i]]++;
            counts[t[i]]--;
        }
        for (auto count : counts)
            if (count.second) return false;
        return true;
    }
};
```

###### Sorting
```C++
# sort(s.begin(), s.end()) 排序(升序)
class Solution {
public:
    bool isAnagram(string s, string t) { 
        sort(s.begin(), s.end());
        sort(t.begin(), t.end());
        return s == t; 
    }
};
```