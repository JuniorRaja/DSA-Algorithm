# 6. Zig Zag Conversion

Created: April 11, 2024 8:50 AM
Course: LeetCode
Level: Medium

# QUESTION

The string "PAYPALISHIRING" is written in a zigzag pattern on a given number of rows like this: (you may want to display this pattern in a fixed font for better legibility)

P A H N A P L S I I G Y I R

And then read line by line: "PAHNAPLSIIGYIR"

Write the code that will take a string and make this conversion given a number of rows:

string convert(string s, int numRows);

**Example 1:**

```
Input: s = "PAYPALISHIRING", numRows = 3
Output: "PAHNAPLSIIGYIR"
```

**Example 2:**

```
Input: s = "A", numRows = 1
Output: "A"
```

**Example 3:**

```
Input: s = "PAYPALISHIRING", numRows = 4
Output: "PINALSIGYAHRPI"
Explanation:
P     I    N
A   L S  I G
Y A   H R
P     I
```

# OBSERVATION

- 

# APPROACH

- Array sort

# SOLUTION

- Init an array for the input row length (row length = arraylen)
- Inti a currRow & director variables
- Iterate through all chars and add the current value at currRow index
- Then, check where should the next element go and update the currRow
- Direction is held as forward and backward with +1 or -1
- Concat the array to return as single string

```csharp
//CODE
public class Solution 
{
    public string Convert(string s, int numRows) 
    {
        if(numRows == 1 || s.Length <= 1)
        {
            return s;
        }

        string[] result = new string[numRows];

        int i = 0, direction = 1;
        foreach(char c in s)
        {
            result[i] += c;

            i += direction;

            if (i == numRows-1 || i==0) direction *= -1;
        }

        return string.Concat(result);
    }
}
```