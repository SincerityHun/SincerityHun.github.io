---
title: Remove Duplicates from Sorted Array II
# date: 2023-09-15 17:10:00 +/-TTTT
categories: [Algorithm, Array/String]
tags: [c++, leet code] # TAG names should always be lowercase
---

### 1. Problem Statement

- [Remove Duplicates from Sorted Array II](https://leetcode.com/problems/remove-duplicates-from-sorted-array-ii/description/?envType=study-plan-v2&envId=top-interview-150)

### 2. Algorithm Design and Approach


### 3. Implementation

```cpp
class Solution
{
public:
    int removeDuplicates(vector<int> &nums)
    {
        int cur = nums[0];
        int flag = 0;
        int len = nums.size();
        for (auto it = nums.begin(); it != nums.end(); it++)
        {
            if (*it == cur)
            {
                if (flag > 1)
                {
                    nums.erase(it);
                    it--;
                    len--;
                }
                else
                {
                    flag++;
                }
            }
            else
            {
                cur = *it;
                flag = 1;
            }
        }
        return len;
    }
};
```

### 4. Example Walkthrough


### 5. Conclusion


