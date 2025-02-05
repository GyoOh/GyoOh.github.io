---
layout: single
title: ' LeetCode : 03. Longest Substring Without Repeating Characters'
categories: coding
tag: [leetcode, blog, jekyll]
author: GyoOh
---

### Problem

```
Given a string s, find the length of the longest substring without repeating characters.
```

---

### Example

```
Example 1:

Input: s = "abcabcbb"
Output: 3
Explanation: The answer is "abc", with the length of 3.
```

```
Example 2:

Input: s = "bbbbb"
Output: 1
Explanation: The answer is "b", with the length of 1.
```

```
Example 3:

Input: s = "pwwkew"
Output: 3
Explanation: The answer is "wke", with the length of 3.
Notice that the answer must be a substring, "pwke" is a subsequence and not a substring.
```

---

### Code

```
var lengthOfLongestSubstring = function(s) {
        let max = 0;
        let str = "";
    for (let i = 0; i < s.length; i++) {
        let char = s.charAt(i);
        let index = str.indexOf(char);
        if (index > -1) {
            str = str.substr(index + 1);
        }
        str += char;
        max = Math.max(max, str.length);
    }
    return max;
};

---

### Reference

@https://leetcode.com/problems/longest-substring-without-repeating-characters/submissions/960798219/

---
