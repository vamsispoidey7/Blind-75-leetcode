# 153. Find Minimum in Rotated Sorted Array

**Problem Link:** https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/

---

## 🖼️ Editorial / Visual Explanation

https://leetcode.com/problems/find-minimum-in-rotated-sorted-array/solutions/158940/beat-100-very-simple-python-very-detaile-pzak/

---

## Binary Search

### 💻 C++ Code
```cpp
class Solution {
public:
    int findMin(vector<int>& nums) {
        int n = nums.size();
        int low = 0, high = n-1;
        while(low<high){
            int mid = low + (high-low)/2;
            if(nums[mid]>nums[high]){
                low = mid+1;
            }else{
                high = mid;
            }
        }
        return nums[low];
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(logN)`
- **Space Complexity:** `O(1)`

---
