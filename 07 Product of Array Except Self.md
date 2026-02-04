# 238. Product of Array Except Self

**Problem Link:** https://leetcode.com/problems/product-of-array-except-self/

---

## 🖼️ Editorial / Visual Explanation

https://leetcode.com/problems/product-of-array-except-self/solutions/1342916/3-minute-read-mimicking-an-interview-by-1fpyp/

---

## One Pass

### 💻 C++ Code
```cpp
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n = nums.size();
        vector<int> leftProduct(n,1), rightProduct(n,1);
        for(int i=1;i<n;i++){
            leftProduct[i] = leftProduct[i-1] * nums[i-1];
        }
        for(int i=n-2;i>=0;i--){
            rightProduct[i] = rightProduct[i+1] * nums[i+1];
        }
        vector<int> result(n,1);
        for(int i=0;i<n;i++){
            result[i] = leftProduct[i] * rightProduct[i];
        }
        return result;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(N)`

---

## Two Pass

### 💻 C++ Code
```cpp
class Solution {
public:
    vector<int> productExceptSelf(vector<int>& nums) {
        int n = nums.size();
        vector<int> result(n,1);
        int currProduct = 1;
        for(int i=0;i<n;i++){
            result[i] *= currProduct;
            currProduct *= nums[i];
        }
        currProduct = 1;
        for(int i=n-1;i>=0;i--){
            result[i] *= currProduct;
            currProduct *= nums[i];
        }
        return result;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---
