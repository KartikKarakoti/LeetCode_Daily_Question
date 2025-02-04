class Solution:
    def maxAscendingSum(self, nums: List[int]) -> int:
        max_sum = cur_sum = nums[0] # start at first num

        for a, b in pairwise(nums): # i in range(len(nums) - 1), [i, i + 1] also works 
            cur_sum = cur_sum + b if a < b else b # subarray either exapnds or is reset 
            max_sum = max(max_sum, cur_sum) # update max sum

        return max_sum
