---
layout: single
title: ' LeetCode : 02. Two Sum'
categories: coding
tag: [leetcode, blog, jekyll]
author: GyoOh
---

### Problem

```
You are given two non-empty linked lists representing two non-negative integers. The digits are stored in reverse order, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.
```

---

### Example

```
Example 1:

Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.
```

```
Example 2:

Input: l1 = [0], l2 = [0]
Output: [0]
```

```
Example 3:

Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
Output: [8,9,9,9,0,0,0,1]
```

---

### Code

```
var addTwoNumbers = function (l1, l2) {
    let firstNum = ""
    let secondNum = "";
    for (let i = l1.length - 1; i > -1; i--) {
        firstNum += l1[i].toString()
    }
    for (let i = l2.length - 1; i > -1; i--) {
        secondNum += l2[i].toString();
    }
    const result = (Number(firstNum) + Number(secondNum)).toString();
    let lastNum = ""
    for (let i = result.length - 1; i > -1; i--) {
        lastNum += result[i]
    }
    return lastNum
};
(addTwoNumbers([2, 4, 3], [5, 6, 4]))


```

---

I needed to use nodeList which can be made by new

```
let current = new ListNode(0);
```

Withs this new list, I needed to make another logic

```
var addTwoNumbers = function(l1, l2) {

    let sum = 0;
    let current = new ListNode(0);
    let result = current;

    while(l1 || l2) {

        if(l1) {
            sum += l1.val;
            l1 = l1.next;
        }

        if(l2) {
            sum += l2.val;
            l2 = l2.next;
        }

        current.next = new ListNode(sum % 10);
        current = current.next;

        sum = sum > 9 ? 1 : 0;
    }

    if(sum) {
        current.next = new ListNode(sum);
    }

    return result.next;
};
```

---

### Reference

@https://leetcode.com/problems/add-two-numbers/solutions/3149937/simple-js-solution-o-max-m-n-time-o-max-m-n-space/

---
