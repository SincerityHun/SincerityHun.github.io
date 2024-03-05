---
title: Kth Smallest Element in a BST
# date: 2023-09-15 17:10:00 +/-TTTT
categories: [Algorithm, Sliding Window]
tags: [c++, leet code] # TAG names should always be lowercase
---

### 1. Problem Statement

- [Kth Smallest Element in a BST](https://leetcode.com/problems/kth-smallest-element-in-a-bst/)

### 2. Algorithm Design and Approach

### 3. Implementation

```cpp
class Solution
{
public:
    int kthSmallest(TreeNode *root, int k)
    {
        vector<TreeNode *> stack;
        TreeNode *node = root;

        while (true)
        {

            while (node != nullptr)
            {
                stack.push_back(node);
                node = node->left;
            }
            node = stack.back();
            stack.pop_back();
            
            if (--k == 0)
                return node->val;
            node = node->right;
        }
    }
};
```

### 4. Example Walkthrough

### 5. Conclusion
- stack으로 제일 왼쪽에 있는 아이템 관리