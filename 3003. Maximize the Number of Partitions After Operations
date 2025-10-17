class Solution:
    def maxPartitionsAfterOperations(self, S: str, K: int) -> int:
        N = len(S)
        A = [1 << (ord(c) - ord("a")) for c in S]

        @cache
        def dp(i, option, mask):
            if i == len(A):
                return 0
            mask2 = mask | A[i]
            if mask2.bit_count() > K:
                ans = 1 + dp(i + 1, option, A[i])
            else:
                ans = dp(i + 1, option, mask2)

            if option:
                for j in range(26):
                    mask2 = mask | (1 << j)
                    if mask2.bit_count() > K:
                        ans = max(ans, 1 + dp(i + 1, 0, 1 << j))
                    else:
                        ans = max(ans, dp(i + 1, 0, mask2))
            
            return ans

        return dp(0, 1, 0) + 1
