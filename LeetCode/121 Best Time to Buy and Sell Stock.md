# 121. Best Time to Buy and Sell Stock

Created: March 6, 2024 11:18 PM
Course: LeetCode
Level: Easy
ID: 20
Last Edited: March 6, 2024 11:21 PM

# Question

Say you have an array for which the ith element is the price of a given stock on day i.

If you were only permitted to complete at most one transaction (i.e., buy one and sell one share of the stock), design an algorithm to find the maximum profit.

Note that you cannot sell a stock before you buy one.

**Example 1:**

```
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

```

**Example 2:**

```
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: In this case, no transactions are done and the max profit = 0.
```

# APPROACH

- Two Pointers

# SOLUTION

- Take the first element of the array
- Compare with the next element
- Calculate profit if then buy price is < sell price (i.e the two elements compared)

```csharp
public class Solution {
    public int MaxProfit(int[] prices) {
        
        int buyPrice = prices[0];
        int profit = 0;

        for(int i = 1; i< prices.Length; i++){
            if(prices[i] < buyPrice){
                buyPrice = prices[i];
            }
            else {
                int currentProfit = prices[i] - buyPrice;
                profit = Math.Max(currentProfit, profit);
            }
        }
        return profit;
    }
}
```