class Solution:
    def maxSubarraySum(self, nums: List[int], k: int) -> int:
        INF = float('inf')
        n = len(nums)
        maxi = sum(nums[:k])
        d = {i : INF for i in range(k)}
        presum = 0
        for i in range(n):
            presum += nums[i]
            if d[i%k]!= INF:
                maxi = max(maxi, presum-d[i%k])
            d[i%k] = min(d[i%k],presum)
            if (i+1)%k == 0:
                maxi = max(maxi,presum)
        return maxi
