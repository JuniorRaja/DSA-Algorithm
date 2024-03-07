# 13. Roman to Integer

Created: March 7, 2024 11:32 PM
Course: LeetCode
Level: Easy

# QUESTION

- Find the numeric values of the input Roman Numerals

```
Symbol      Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```

**Example 1:**

```
Input: s = "III"
Output: 3
Explanation: III = 3.
```

**Example 2:**

```
Input: s = "LVIII"
Output: 58
Explanation: L = 50, V= 5, III = 3.
```

**Example 2:**

```
Input: s = "MCMXCIV"
Output: 1994
Explanation: M = 1000, CM = 900, XC = 90 and IV = 4.
```

# OBSERVATION

- An input string of Roman Numerals should be represented as Int

# APPROACH

- 

# SOLUTION

- Code the given Roman Numerals - Numeric values
- Initialize an var result ////////// doubt:: with value of the last element in the array
- Iterate through the array from right to left
- compare the left value with the previous (right)
- Add or subtract the current previous val to the result
- do the same for all elements in the array

```csharp
//CODE
public class Solution {
    public int RomanToInt(string s) {
        var chars = s.ToCharArray();
        int result = 0;
        int currentVal = 0;
        
        for(int i = 0; i < chars.Length -1; i++){
            currentVal = RomanToNumerals(chars[i]);
            result += (RomanToNumerals(chars[i+1]) > currentVal ? -1 : 1) * currentVal;
        }
    return result +  RomanToNumerals(chars[chars.Length - 1]);
    }

    public int RomanToNumerals(char c){
        switch(c) {
            case 'I' : return 1;
            case 'V' : return 5;
            case 'X' : return 10;
            case 'L' : return 50;
            case 'C' : return 100;
            case 'D' : return 500;
            case 'M' : return 1000;
        }
        return 0;
    }
}
```