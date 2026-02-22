# 338. Counting Bits

**Problem Link:** https://leetcode.com/problems/counting-bits/

---

## 🖼️ Editorial / Visual Explanation

https://www.youtube.com/watch?v=uwOz378g3ew

---

## O(NlogN) Solution

### 💻 C++ Code
```cpp
class Solution {
public:
    vector<int> countBits(int n) {
        vector<int> result(n+1);
        for(int i=0;i<n+1;i++){
            result[i] = __builtin_popcount(i);
        }
        return result;
    }
};
```
```cpp
class Solution {
public:
    int numberOfBits(int n){
        int count = 0;
        while(n>0){
            n = (n&(n-1));
            count++;
        }
        return count;
    }
    vector<int> countBits(int n) {
        vector<int> result(n+1);
        for(int i=0;i<n+1;i++){
            result[i] = numberOfBits(i);
        }
        return result;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(NlogN)`
- **Space Complexity:** `O(1)`

---

## O(N) solution

### 💻 C++ Code
```cpp
class Solution {
public:
    vector<int> countBits(int n) {
        if(n==0) return {0};
        vector<int> result(n+1);
        for(int i=1;i<n+1;i++){
            if(i%2==0){
                result[i] = result[i/2];
            }else{
                result[i] = result[i/2] + 1;
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
