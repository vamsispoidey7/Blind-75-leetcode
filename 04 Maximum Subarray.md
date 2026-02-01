# 53. Maximum Subarray

**Problem Link:** https://leetcode.com/problems/maximum-subarray/

---

## 🖼️ Editorial / Visual Explanation

<img width="933" height="7013" alt="053  Maximum Subarray" src="https://github.com/user-attachments/assets/9b00b697-d824-412a-89e4-dec1379376a2" />

---

## Brute Force Approach

### 💻 C++ Code
```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int n = nums.size();
        int maxSum = INT_MIN;
        for(int i=0;i<n;i++){
            int currSum = 0;
            for(int j=i;j<n;j++){
                currSum += nums[j];
                maxSum = max(maxSum,currSum);
            }
        }
        return maxSum;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N^2)`
- **Space Complexity:** `O(1)`

---

## Kadane's Algorithm

### 💻 C++ Code
```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int n = nums.size();
        int currSum = 0, maxSum = INT_MIN;
        for(int i=0;i<n;i++){
            currSum += nums[i];
            maxSum = max(maxSum,currSum);
            if(currSum<0){
                currSum = 0;
            }
        }
        return maxSum;
    }
};
```

```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int n = nums.size();
        int currSum = 0, maxSum = INT_MIN;
        for(int i=0;i<n;i++){
            currSum += nums[i];
            maxSum = max(maxSum,currSum);
            currSum = max(0,currSum);
        }
        return maxSum;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---

## Divide and Conquer
### 💻 C++ Code
```cpp
class Solution {
public:
    int f(int start,int end,vector<int>& nums){
        if(start>end) return INT_MIN;
        int mid = start + (end-start)/2;
        int leftMax = 0, rightMax = 0;
        int sum = 0;
        for(int i=mid-1;i>=start;i--){
            sum += nums[i];
            leftMax = max(leftMax,sum);
        }
        sum = 0;
        for(int i=mid+1;i<=end;i++){
            sum += nums[i];
            rightMax = max(rightMax,sum);
        }
        return max({leftMax+nums[mid]+rightMax,f(start,mid-1,nums),f(mid+1,end,nums)});
    }
    int maxSubArray(vector<int>& nums) {
        return f(0,nums.size()-1,nums);
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(NlogN)`
- **Space Complexity:** `O(logN)`

---
