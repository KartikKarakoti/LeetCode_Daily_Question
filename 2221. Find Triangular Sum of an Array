class Solution:
    def triangularSum(self, nums: List[int]) -> int:
        length = len(nums)
        coefficient = 1
        result = 0
        for i in range(length):
            result += nums[i] * coefficient
            coefficient = coefficient * (length - 1 - i) // (i + 1)
        return result % 10
