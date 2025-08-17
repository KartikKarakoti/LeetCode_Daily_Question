class Solution:
    def new21Game(self, n: int, k: int, maxPts: int) -> float:
        if k == 0 or n >= k - 1 + maxPts:
            return 1.0
        dp = [0.0] * (n + 1)
        dp[0] = 1.0
        window_sum, probability = 1.0, 0.0
        for i in range(1, n + 1):
            dp[i] = window_sum / maxPts
            if i < k:
                window_sum += dp[i]
            else:
                probability += dp[i]
            if i >= maxPts:
                window_sum -= dp[i - maxPts]
        return probability
