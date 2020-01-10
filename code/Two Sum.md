# LeetCode 1. Two Sum
###### tags: `leetcode` `python`
## Two Sum

Question:  
Given an array of integers, return indices of the two numbers such that they add up to a specific target.   

You may assume that each input would have exactly one solution, and you may not use the same element twice.  

Example:  
```shell
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```
## mycode
* 第一次提交
    ```python
    class Solution:
        def twoSum(self, nums: List[int], target: int) -> List[int]:            
            for o_idx in range(len(nums)):
                for i_idx, num in enumerate(nums):
                    # 當內外索引相同的時候就不處理
                    if o_idx == i_idx:
                        continue

                    if nums[o_idx] + num == target:
                        return [o_idx, i_idx]
    ```    
    這次提交之後得到Time Limit Exceeded的失敗訊息，第一次做才發現，原來不是只有帳面上的需求..    

* 第二次提交
    ```python
    class Solution:
        def twoSum(self, nums: List[int], target: int) -> List[int]:
            for idx, num in enumerate(nums):
                if target - num in nums[idx + 1: ]:
                    return [idx, nums[idx + 1: ].index(target - num) + idx + 1]
    ```
    這次提交想法上是以減少來找值是否存在list之內，如果存在就取得該值的索引之後回傳
    

## result
Runtime: 884 ms, faster than 24.83% of Python3 online submissions for Two Sum.  
Memory Usage: 13.8 MB, less than 75.81% of Python3 online submissions for Two Sum.  