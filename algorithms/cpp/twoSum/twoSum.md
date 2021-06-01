# Two Sum
1. 暴力循环法
时间复杂度O(n^2) 空间复杂度O(1)
2. 使用unordered_map通过key-value形式找到对应关系
时间复杂度O(n) 空间复杂度O(n)

---

第一次刷题:第一种解法
```
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> ret;
        for(int i = 0; i < nums.size(); ++i){
            for(int j = i + 1; j < nums.size(); ++j){
                if (nums[i] + nums[j] == target){
                    return {i,j};
                }
            }
        }
        
        return ret;
    }
```

第二种解法
```
    vector<int> twoSum(vector<int>& nums, int target) {
        vector<int> ret;
        unordered_map<int, int> tmp;
        for(int i = 0; i < nums.size(); ++i){
            if(tmp.count(target - nums[i])){
                ret.push_back(tmp[target - nums[i]]);
                ret.push_back(i);
                
                return ret;
            }
            else{
                tmp[nums[i]] = i;
            }
        }
        
        return ret;
    }
```

**总结**
[map与unordered_map的区别](https://www.jianshu.com/p/81ac9b6c2419)