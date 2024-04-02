# 12. Integer to Roman

Created: April 2, 2024 11:36 PM
Course: LeetCode
Level: Medium

# QUESTION

Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.

Symbol Value I 1 V 5 X 10 L 50 C 100 D 500 M 1000

For example, two is written as II in Roman numeral, just two one's added together. Twelve is written as, XII, which is simply X + II. The number twenty seven is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

- I can be placed before V (5) and X (10) to make 4 and 9.
- X can be placed before L (50) and C (100) to make 40 and 90.
- C can be placed before D (500) and M (1000) to make 400 and 900.

Given an integer, convert it to a roman numeral. Input is guaranteed to be within the range from 1 to 3999.

**Example 1:**

```
Input: num = 3
Output: "III"
Explanation: 3 is represented as 3 ones.
```

**Example 2:**

```
Input: num = 58
Output: "LVIII"
Explanation: L = 50, V = 5, III = 3.
```

**Example 3:**

```
Input: num = 1994
Output: "MCMXCIV"
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
```

# OBSERVATION

- The list of key value pairs are incomplete
- The special conditions mentioned below must be included

# APPROACH

- 

# SOLUTION

- Add the addl. conditions given below to the Key Value set
- Declare it as a array
- Iterate through the array
- If num is ≥ the current key (i.e. the numeric val), append the respective value (i.e. Roman val) to the result
- the loop will continue till num = 0

```csharp
//CODE
public class Solution {
    public string IntToRoman(int num) {
        var result = new StringBuilder();
        var map = new Dictionary<int, string>
        {
            { 1000, "M"},
            { 900, "CM"},
            { 500, "D"},
            { 400, "CD" },
            { 100, "C" },
            { 90, "XC" },
            { 50, "L" },
            { 40, "XL" },
            { 10, "X" },
            { 9, "IX" },
            { 5, "V" },
            { 4, "IV" },
            { 1, "I" },
        };

        foreach(var KeyVal in map){
            while(num >= KeyVal.Key){
                result.Append(KeyVal.Value);
                num -= KeyVal.Key;
            }
            
            if(num == 0){
                    return result.ToString();
            }
        }
        return result.ToString();
    }
}
```