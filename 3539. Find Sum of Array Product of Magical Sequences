class Solution(object):
    def magicalSum(self, m, k, nums):
        """
        :type m: int
        :type k: int
        :type nums: List[int]
        :rtype: int
        """
        M = 10**9 + 7
        l = len(nums)
        d = {}
        def f(r, n, i, c):
            if r < 0 or n < 0 or r + bin(c).count('1') < n:
                return 0
            if r == 0:
                return 1 if n == bin(c).count('1') else 0
            if i >= l:
                return 0
            key = (r, n, i, c)
            if key in d:
                return d[key]
            res = 0
            for t in range(r + 1):
                w = 1
                for j in range(t):
                    w = w * (r - j) // (j + 1)
                w %= M
                v = pow(nums[i], t, M)
                nc = c + t
                res = (res + w * v % M * f(r - t, n - (nc % 2), i + 1, nc // 2)) % M
            d[key] = res
            return res
        return f(m, k, 0, 0)
