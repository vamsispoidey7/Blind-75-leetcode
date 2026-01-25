# 1. Two Sum

**Problem Link:** https://leetcode.com/problems/two-sum/

---

## 🖼️ Editorial / Visual Explanation

<img width="933" height="3202" alt="001  Two Sum" src="https://github.com/user-attachments/assets/ecf44415-8f63-4775-88b1-03633df68aa1" />


---

## Brute Force Approach

### 💻 C++ Code
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int n = nums.size();
        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                if(nums[i]+nums[j]==target){
                    return {i,j};
                }
            }
        }
        return {};
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N^2)`
- **Space Complexity:** `O(1)`

---

## Two Pass Approach

### 💻 C++ Code
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int n = nums.size();
        unordered_map<int,int> mp;
        for(int i=0;i<n;i++){
            mp[nums[i]] = i;
        }
        for(int i=0;i<n;i++){
            int complement = target-nums[i];
            if(mp.find(complement)!=mp.end() && mp[complement]!=i){
                return {i,mp[complement]};
            }
        }
        return {};
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(N)`

---

## One Pass Approach

### 💻 C++ Code
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        int n = nums.size();
        unordered_map<int,int> mp;
        for(int i=0;i<n;i++){
            int complement = target-nums[i];
            if(mp.find(complement)!=mp.end()){
                return {i,mp[complement]};
            }
            mp[nums[i]] = i;
        }
        return {};
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(N)`

---
