### 题目
[Distribute Candies](https://leetcode-cn.com/problems/distribute-candies/submissions/)
### 思路
364ms 70.84%

找到所有不重复字符。如果大于一半就返回count，小于就返回不重复个数
### 代码
```c++
class Solution {
public:
    int distributeCandies(vector<int>& candies) {
        int count=candies.size()/2;
        unordered_set<int> us;
        for(auto p:candies){
            us.insert(p);
        }
        return us.size()>count?count:us.size();
    }
};
```
