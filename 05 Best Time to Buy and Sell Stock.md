# 121. Best Time to Buy and Sell Stock

**Problem Link:** https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

---

## 🖼️ Editorial / Visual Explanation

https://www.youtube.com/watch?v=excAOvwF_Wk

---

## Brute Force Approach

### 💻 C++ Code
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int n = prices.size();
        int profitMax = 0;
        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                profitMax = max(profitMax,prices[j]-prices[i]);
            }
        }
        return profitMax;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N^2)`
- **Space Complexity:** `O(1)`

---

## Optimised Approach

### 💻 C++ Code
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int n = prices.size();
        int minPrice = prices[0];
        int maxProfit = 0;
        for(int i=1;i<n;i++){
            maxProfit = max(maxProfit,prices[i]-minPrice);
            minPrice = min(minPrice,prices[i]);
        }
        return maxProfit;
    }
};
```

### ⏱ Complexity
- **Time Complexity:** `O(N)`
- **Space Complexity:** `O(1)`

---

## Kadane's Algorithm

Explanation : https://leetcode.com/problems/best-time-to-buy-and-sell-stock/solutions/39038/kadanes-algorithm-since-no-one-has-menti-1wai/

### 💻 C++ Code
```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int n = prices.size();
        int currSum = 0, maxSum = 0;
        for(int i=1;i<n;i++){
            currSum += prices[i] - prices[i-1];
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
