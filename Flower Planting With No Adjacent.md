### 题目
[1042. Flower Planting With No Adjacent](https://leetcode-cn.com/problems/flower-planting-with-no-adjacent/submissions/)
### 思路
288ms 52.82%

### 代码
```c++
class Solution {
public:
    vector<int> gardenNoAdj(int N, vector<vector<int>>& paths) {
        vector<int> res(N,0);
        vector<vector<int>> v(N,vector<int>());
        for(int i=0;i<paths.size();i++){
            v[paths[i][0]-1].push_back(paths[i][1]-1);
            v[paths[i][1]-1].push_back(paths[i][0]-1);
        }
        
        for(int i=0;i<N;i++){
            set<int> s={1,2,3,4};
            for(int j=0;j<v[i].size();j++){
                if(s.find(res[v[i][j]])!=s.end()){
                    s.erase(res[v[i][j]]);
                }
            }
            res[i]=*s.begin();                    
        }
        return res;
    }
};
```
