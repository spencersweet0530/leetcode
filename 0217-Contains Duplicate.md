## 217. Contains Duplicate
[leetcode 217. Contains Duplicate](https://leetcode.com/problems/contains-duplicate/)

Given an integer array nums, return true if any value appears at least twice in the array, and return false if every element is distinct.

Example 1:
* Input: nums = [1,2,3,1]
* Output: true

Example 2:
* Input: nums = [1,2,3,4]
* Output: false

Example 3:
* Input: nums = [1,1,1,3,3,4,3,2,4,2]
* Output: true

Python：
```python
# len() return (char, list, tuple)內有多少個數
# set() 集合不會包含重複的資料
class Solution(object):
    def containsDuplicate(self, nums):
        return len(nums) != len(set(nums))
```

C++：
```C++
#include <set>
using namespace std;

class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        return nums.size() > set<int>(nums.begin(), nums.end()).size();        
    }
};
```