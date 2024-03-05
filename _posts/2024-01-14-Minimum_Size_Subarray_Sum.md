---
title: Minimum Size Subarray Sum
# date: 2023-09-15 17:10:00 +/-TTTT
categories: [Algorithm, Sliding Window]
tags: [c++, leet code] # TAG names should always be lowercase
---

### 1. Problem Statement

- [Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/description/?envType=study-plan-v2&envId=top-interview-150)

### 2. Algorithm Design and Approach

### 3. Implementation

```cpp
class Solution
{
public:
    int minSubArrayLen(int target, vector<int> &nums)
    {
        int l = 0;
        int r = 0;
        int limit = nums.size();
        int window =  limit + 1; // r - l + 1
        int cur_sum = nums[l];
        int flag = 0; //0은 초기 , 1은 전에 l 증가, 2는 전에 r 증가
        while (l < limit && r < limit)
        {
            //현재 합 구해
            if (flag == 1)
            {
                cur_sum -= nums[l - 1];
            }
            else if (flag == 2)
            {
                cur_sum += nums[r];
            }
            //합이 target보다 크거나 같아?
            if(cur_sum >= target)
            {
                window = (r - l + 1) < window ? (r-l+1): window;
                cur_sum -= nums[l];
                l++;
                flag = 1;
            }
            else
            {
                r++;
                flag = 2;
            }
        }
        return (window == limit + 1) ? 0 : window;
    }
};
static const auto _____ = []()
{
    ios::sync_with_stdio(false);
    cin.tie(0);
    return 0;
}();
```

### 4. Example Walkthrough

### 5. Conclusion

- 조건문을 최소화해야한다.
  -> while (l < limit && r < limit) 대신에 while(l<=r)으로 사용할 수 있는 알고리즘
  -> flag을 사용하지 않고 l과 r 포인터가 움직일 때 current sum을 업데이트 + r의 유효성 검사
- 아래 sync_with_stdio를 사용해 input, output 시간을 줄일 수 있다.
