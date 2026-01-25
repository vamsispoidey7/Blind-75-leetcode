# 167. Two Sum II - Input Array Is Sorted

**Problem Link:** https://leetcode.com/problems/two-sum-ii-input-array-is-sorted/

---

## 🖼️ Editorial / Visual Explanation

<img width="933" height="1524" alt="167  Two Sum II - Input Array Is Sorted" src="https://github.com/user-attachments/assets/3826a27b-a4f0-4154-bb7c-aac263d123a4" />

---

## Approach

### 💻 C++ Code
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
        int n = numbers.size();
        int low=0, high=n-1;
        while(low<high){
            int sum = numbers[low] + numbers[high];
            if(sum==target){
                return {low+1,high+1};
            }else if(sum<target){
                low++;
            }else{
                high--;
            }
        }
        return {};
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---

## Followup : Using long long

Cast **at least one operand** to `long long` before addition so the sum is computed in **64-bit**.

### 💻 C++ Code
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& numbers, int target) {
        int n = numbers.size();
        int low=0, high=n-1;
        while(low<high){
            long long sum = (long long)numbers[low] + numbers[high];
            if(sum==target){
                return {low+1,high+1};
            }else if(sum<target){
                low++;
            }else{
                high--;
            }
        }
        return {};
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---
