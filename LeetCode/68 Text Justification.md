# 68. Text Justification

Created: June 21, 2024 7:32 AM
Course: LeetCode

# QUESTION

Given an array of strings `words` and a width `maxWidth`, format the text such that each line has exactly `maxWidth` characters and is fully (left and right) justified.

You should pack your words in a greedy approach; that is, pack as many words as you can in each line. Pad extra spaces `' '` when necessary so that each line has exactly `maxWidth` characters.

Extra spaces between words should be distributed as evenly as possible. If the number of spaces on a line does not divide evenly between words, the empty slots on the left will be assigned more spaces than the slots on the right.

For the last line of text, it should be left-justified, and no extra space is inserted between words.

**Note:**

- A word is defined as a character sequence consisting of non-space characters only.
- Each word's length is guaranteed to be greater than `0` and not exceed `maxWidth`.
- The input array `words` contains at least one word

**Example 1:**

```
Input: words = ["This", "is", "an", "example", "of", "text", "justification."], maxWidth = 16
Output:
[
   "This    is    an",
   "example  of text",
   "justification.  "
]
```

**Example 2:**

```
Input: words = ["What","must","be","acknowledgment","shall","be"], maxWidth = 16
Output:
[
  "What   must   be",
  "acknowledgment  ",
  "shall be        "
]
Explanation: Note that the last line is "shall be    " instead of "shall     be", because the last line must be left-justified instead of fully-justified.
Note that the second line is also left-justified because it contains only one word.
```

# OBSERVATION

- 

# APPROACH

## **Modulo-based Space Distribution**

To solve the "Text Justification" problem using this approach, we pack words into each line using a greedy strategy. We then distribute spaces among the words on each line, using modulo arithmetic to decide where to place the extra spaces.

### **Key Data Structures:**

- **List**: To store the current words for a line and the result.

# SOLUTION

1. **Initialization**:
    - We start by initializing empty lists for the result and the current line words.
    - A counter is also initialized to keep track of the total length of words in the current line.
2. **Processing Each Word**:
    - For each word, we check if adding the next word to the current line would make it exceed the maximum width.
    - If it does, we proceed to justify the current line. This involves distributing spaces among the words. The modulo arithmetic is handy here, ensuring that extra spaces are evenly spread among the words.
    - Once the line is justified, we reset the lists and counter for the next line.
    - A special case is the last line, where we simply left-justify the words.
3. **Wrap-up**:
    - Once all the words are processed and lines are justified, we return the result list.

```csharp
//CODE
```