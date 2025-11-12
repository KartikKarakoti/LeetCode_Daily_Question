class Solution:
    def minOperations(self, nums: List[int]) -> int:
        ones = nums.count(1)
        if ones: return len(nums)-ones
        diff = inf 
        for i in range(len(nums)): 
            g = nums[i]
            for j in range(i+1, len(nums)):
                g = gcd(g, nums[j])
                if g == 1: diff = min(diff, j-i)
        return -1 if diff == inf else diff + len(nums) - 1
