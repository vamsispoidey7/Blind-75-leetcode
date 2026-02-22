# 268. Missing Number

**Problem Link:** https://leetcode.com/problems/missing-number/

---

## 🖼️ Editorial / Visual Explanation

<img width="933" height="4896" alt="268  Missing Number" src="https://github.com/user-attachments/assets/b4327df8-5770-4e7a-9fdf-4a7e03e0e498" />

---

## Using Sum

### 💻 C++ Code
```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int sum = 0;
        for(int i=0;i<n;i++){
            sum += i;
            sum -= nums[i];
        }
        sum += n;
        return sum;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---

## Using XOR

### 💻 C++ Code
```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n = nums.size();
        int missing_number = 0;
        for(int i=0;i<n;i++){
            missing_number ^= nums[i];
        }
        for(int i=0;i<=n;i++){
            missing_number ^= i;
        }
        return missing_number;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---
