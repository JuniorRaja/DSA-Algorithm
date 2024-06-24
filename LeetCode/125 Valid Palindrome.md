# 125. Valid Palindrome

Created: June 24, 2024 8:03 AM
Course: LeetCode

# QUESTION

A phrase is a **palindrome** if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string `s`, return `true` *if it is a **palindrome**, or* `false` *otherwise*.

**Example 1:**

```
Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
```

**Example 2:**

```
Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.
```

# OBSERVATION

- char should be cleaned (only alphanumeric)
- char should be lowercase

# APPROACH

- Two pointers

# SOLUTION

- Two pointers - at start and end
- check both pointers for invalid char
- compare both char

```csharp
//CODE
public class Solution {
    public bool IsPalindrome(string s) {
        if (s.Length <= 1) {
            return true;
        }
        
        int i = 0, j = s.Length - 1;
        while (j > i) {
            if (!char.IsLetterOrDigit(s[i])) {
                i++;
                continue;
            }
            if (!char.IsLetterOrDigit(s[j])) {
                j--;
                continue;
            }
            if (char.ToLower(s[i++]) != char.ToLower(s[j--])) {
                return false;
            }
        }

        // for (int i = 0; j = s.Length - 1; j > i;) {
        //     if (!char.IsLetterOrDigit(s[i])) {
        //         i++;
        //         continue;
        //     }
        //     if (!char.IsLetterOrDigit(s[j])) {
        //         j++;
        //         continue;
        //     }
        //     if(char.ToLower(s[i++] != char.ToLower(s[j--])){
        //         return false;
        //     }
        // }

        return true;
    }
}
```