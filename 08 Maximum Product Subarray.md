# 152. Maximum Product Subarray

**Problem Link:** https://leetcode.com/problems/maximum-product-subarray/

---

## 🖼️ Editorial / Visual Explanation

https://www.youtube.com/watch?v=hnswaLJvr6g

---

## Brute Force

### 💻 C++ Code
```cpp
class Solution {
public:
    int maxProduct(vector<int>& nums) {
        int n = nums.size();
        int productMax = INT_MIN;
        for(int i=0;i<n;i++){
            int product = 1;
            for(int j=i;j<n;j++){
                product *= nums[j];
                productMax = max(productMax, product);
            }
        }
        return productMax;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N^2)`
- **Space Complexity:** `O(1)`

---

## Optimal

### 💻 C++ Code
```cpp
class Solution {
public:
    int maxProduct(vector<int>& nums) {
        int n = nums.size();
        int prefixProduct = 1;
        int suffixProduct = 1;
        int result = INT_MIN;
        for(int i=0;i<n;i++){
            if(prefixProduct==0) prefixProduct = 1;
            if(suffixProduct==0) suffixProduct = 1;
            prefixProduct *= nums[i];
            suffixProduct *= nums[n-i-1];
            result = max({result, prefixProduct, suffixProduct});
        }
        return result;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---
