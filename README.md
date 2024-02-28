# DSA-Squares-of-a-Sorted-Array
Given an integer array nums sorted in non-decreasing order, return an array of the squares of each number sorted in non-decreasing order.

```
Input: nums = [-4,-1,0,3,10]
Output: [0,1,9,16,100]
Explanation: After squaring, the array becomes [16,1,0,9,100].
After sorting, it becomes [0,1,9,16,100].
```

```
class Solution:
    def sortedSquares(self, nums: List[int]) -> List[int]:
        n=len(nums)
        result=[0]*n
        left=0
        right=n-1
        for i in range(right,-1,-1):
            if abs(nums[left])<abs(nums[right]):
                square=nums[right]
                right-=1
            else:
                square=nums[left]
                left+=1
            result[i]=square*square
        return result
        
```
