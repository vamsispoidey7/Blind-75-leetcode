# 191. Number of 1 Bits

**Problem Link:** https://leetcode.com/problems/number-of-1-bits/

---

## 🖼️ Editorial / Visual Explanation

<img width="933" height="2320" alt="191  Number of 1 Bits" src="https://github.com/user-attachments/assets/f4056c1d-ab5a-439a-9fe5-93c484f7fb4c" />

---

## Approach 1

### 💻 C++ Code
```cpp
class Solution {
public:
    int hammingWeight(int n) {
        int count = 0;
        while(n>0){
            count = count + (n&1);
            n = n>>1;
        }
        return count;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(1)`
- **Space Complexity:** `O(1)`

---

## Approach 2

### 💻 C++ Code
```cpp
class Solution {
public:
    int hammingWeight(int n) {
        int count = 0;
        while(n>0){
            n = (n&(n-1));
            count++;
        }
        return count;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---
