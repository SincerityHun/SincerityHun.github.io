---
title: Ugly Number
# date: 2023-09-15 17:10:00 +/-TTTT
categories: [Algorithm, Variables & Operators and Control Flow]
tags: [c++, leet code] # TAG names should always be lowercase
---

### 1. Problem Statement

- [Ugly Number](https://leetcode.com/problems/ugly-number/)
- [My Code](https://github.com/SincerityHun/coding_test>)

### 2. Algorithm Design and Approach

- greedy
- Using While Loop to check prime number in n

### 3. Implementation

```cpp
#include <iostream>
using namespace std;

class Solution
{
public:
    bool isUgly(int n)
    {
        while ((n % 5) == 0 && (n >= 5))
        {
            n /= 5;
        }
        while ((n % 3) == 0 && (n >= 3))
        {
            n /= 3;
        }
        while ((n % 2) == 0 && (n >= 2))
        {
            n /= 2;
        }
        if (n != 1)
        {
            return false;
        }
        return true;
    }
};
```

### 4. Example Walkthrough

> n = 6

- true

> n = 1

- false

> n = 14

- false

### 5. Conclusion

- "%=" Operator changes value of origin left value
- Using "If" and "&&" Operator is not good for minimize time complexity.
