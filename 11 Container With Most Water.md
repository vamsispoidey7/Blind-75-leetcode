# 11. Container With Most Water

**Problem Link:** https://leetcode.com/problems/container-with-most-water/

---

## 🖼️ Editorial / Visual Explanation

https://www.youtube.com/watch?v=w7ftYsZtIbs

---

## Brute Force

### 💻 C++ Code
```cpp
class Solution {
public:
    int maxArea(vector<int>& height) {
        int n = height.size();
        int result = 0;
        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                int width = j - i;
                int currHeight = min(height[i],height[j]);
                result = max(result,width*currHeight);
            }
        }
        return result;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N^2)`
- **Space Complexity:** `O(1)`

---

## Two Pointers Optimal

First start with max width. So think of two pointer approach.
Now we try to decrease the width. So best option is move from shorter heighter and look for better right.

### 💻 C++ Code
```cpp
class Solution {
public:
    int maxArea(vector<int>& height) {
        int n = height.size();
        int result = 0;
        int left = 0, right = n-1;
        while(left<right){
            int width = right - left;
            int currHeight = min(height[left],height[right]);
            result = max(result,width*currHeight);
            if(height[left]<=height[right]){
                left++;
            }else{
                right--;
            }
        }
        return result;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---
