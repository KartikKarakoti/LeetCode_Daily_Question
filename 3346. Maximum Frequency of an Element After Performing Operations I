class Solution:
    def maxFrequency(self, nums: List[int], k: int, numOperations: int) -> int:

        max_value = max(nums) + 1
        max_freq = 0

        frequency = [0] * max_value
        for number in nums:
            frequency[number] += 1

        curr = sum(frequency[:k])
        prev = 0
        target = 0
        increment = 0

        for target in range(max_value):

            curr -= frequency[target]

            if target < max_value - k: curr += frequency[target + k]
            if target > 0: prev += frequency[target - 1]
            if target > k + 1: prev -= frequency[target - (k + 1)]

            increment = min(numOperations, curr + prev)

            max_freq = max(max_freq, frequency[target] + increment)

        return max_freq
