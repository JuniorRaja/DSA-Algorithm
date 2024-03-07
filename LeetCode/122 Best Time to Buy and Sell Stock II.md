# 122. Best Time to Buy and Sell Stock II

Created: March 7, 2024 8:28 AM
Course: LeetCode
Level: Medium

# QUESTION

- Design an algorithm to find the maximum profit. You may complete as many transactions as you like (i.e., buy one and sell one share of the stock multiple times).
- Note: You may not engage in multiple transactions at the same time (i.e., you must sell the stock before you buy again).

**Example 1:**

```
Input: prices = [7,1,5,3,6,4]
Output: 7
Explanation: Buy on day 2 (price = 1) and sell on day 3 (price = 5), profit = 5-1 = 4.
Then buy on day 4 (price = 3) and sell on day 5 (price = 6), profit = 6-3 = 3.
Total profit is 4 + 3 = 7.
```

**Example 2:**

```
Input: prices = [1,2,3,4,5]
Output: 4
Explanation: Buy on day 1 (price = 1) and sell on day 5 (price = 5), profit = 5-1 = 4.
Total profit is 4.
```

**Example 3:**

```
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: There is no way to make a positive profit, so we never buy the stock to achieve the maximum profit of 0.
```

# OBSERVATION

- Find the MAX profit obtainable
- Can do any number of txns

# APPROACH

- Using one pointer

# SOLUTION

- Iterate thought the loop by comparing price[ i - 1] with price of [ i ] where i should be 1
- if price[ i - 1] is lesser than price[ i ], then we get the difference between these (i.e profit)

```csharp
//CODE
public class Solution {
    public int MaxProfit(int[] prices) {
                
        int profit = 0;

        for(int i = 1; i< prices.Length; i++){
            if(prices[i] > prices[i-1]){
                profit += prices[i] - prices[i-1];
            }
        }
        return profit;
    }
}
```

![Untitled](122%20Best%20Time%20to%20Buy%20and%20Sell%20Stock%20II%20492c5da9c94843eeb8963713c13bb597/Untitled.png)