class Solution:
    def findXSum(self, nums, k, x):
        n = len(nums)
        result = []

        for i in range(n - k + 1):
            window = nums[i:i + k]
            freq = Counter(window)
            sorted_freq = sorted(freq.items(), key=lambda a: (-a[1], -a[0]))
            top_x = set(num for num, _ in sorted_freq[:x])
            x_sum = sum(num for num in window if num in top_x)
            result.append(x_sum)

        return result
