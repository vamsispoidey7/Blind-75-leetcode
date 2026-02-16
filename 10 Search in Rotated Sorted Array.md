# 33. Search in Rotated Sorted Array

**Problem Link:** https://leetcode.com/problems/search-in-rotated-sorted-array/

---

## 🖼️ Editorial / Visual Explanation

https://www.youtube.com/watch?v=5qGrJbHhqFs

---

## Binary Search

### 💻 C++ Code
```cpp
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int n = nums.size();
        int low = 0, high = n-1;
        while(low<=high){
            int mid = low + (high-low)/2;
            if(nums[mid]==target) return mid;
            if(nums[low]<=nums[mid]){
                if(nums[low]<=target && target<nums[mid]){
                    high = mid-1;
                }else{
                    low = mid+1;
                }
            }else{
                if(nums[mid]<target && target<=nums[high]){
                    low = mid+1;
                }else{
                    high = mid-1;
                }
            }
        }
        return -1;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(logN)`
- **Space Complexity:** `O(1)`

---
