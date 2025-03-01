class Solution:
    def applyOperations(self, nums: List[int]) -> List[int]:
        n = len(nums)
        j = 0 # index of first zero
        for i in range(n):
            if i + 1 < n and nums[i] == nums[i + 1]: # check if should apply operation
                nums[i] *= 2 
                nums[i + 1] = 0

            if nums[i] != 0:
                nums[i], nums[j] = nums[j], nums[i] # swap zero and non-zero
                j += 1 # j + 1 for next zero index
                
        return nums
