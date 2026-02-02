# 217. Contains Duplicate

**Problem Link:** https://leetcode.com/problems/contains-duplicate/

---

## 🖼️ Editorial / Visual Explanation

<img width="933" height="3315" alt="217  Contains Duplicate" src="https://github.com/user-attachments/assets/e0990e08-b42b-4d1b-9d26-c46afde0a0da" />

---

## Brute Force Approach

### 💻 C++ Code
```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        int n = nums.size();
        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                if(nums[i]==nums[j]){
                    return true;
                }
            }
        }
        return false;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N^2)`
- **Space Complexity:** `O(1)`

---

## Using sorting

### 💻 C++ Code
```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        int n = nums.size();
        for(int i=1;i<n;i++){
            if(nums[i]==nums[i-1]){
                return true;
            }
        }
        return false;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(NlogN)`
- **Space Complexity:** `O(1)`

---

## Using Set

### 💻 C++ Code
```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_set<int> s;
        int n = nums.size();
        for(int i=0;i<n;i++){
            if(s.find(nums[i])!=s.end()){
                return true;
            }
            s.insert(nums[i]);
        }
        return false;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(N)`

---
