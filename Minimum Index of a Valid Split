class Solution:
    def minimumIndex(self, nums: List[int]) -> int:
        lcount = 0
        dominant, rcount = max(Counter(nums).items(), key=lambda x: x[1])
        for i, x in enumerate(nums):
            lcount += x == dominant
            rcount -= x == dominant
            if lcount > (i + 1) // 2 and rcount > (len(nums) - (i + 1)) // 2:
                return i
        return -1
