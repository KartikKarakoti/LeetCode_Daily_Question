from functools import lru_cache

class Solution:
    def earliestAndLatest(self, n: int, firstPlayer: int, secondPlayer: int) -> list[int]:
        @lru_cache(None)
        def dp(n, i, j):
            if i + j == n + 1:
                return (1, 1)
            pairs = n // 2
            other = []
            for k in range(1, pairs + 1):
                left, right = k, n - k + 1
                if left != i and left != j and right != i and right != j:
                    other.append((left, right))
            mid = (n + 1) // 2
            m = (n + 1) // 2
            early, latest = float('inf'), 0
            tot = len(other)
            for mask in range(1 << tot):
                surv = []
                for idx, (left, right) in enumerate(other):
                    if (mask >> idx) & 1:
                        surv.append(right)
                    else:
                        surv.append(left)
                surv.append(i)
                surv.append(j)
                if (n % 2 == 1) and mid != i and mid != j:
                    surv.append(mid)
                surv.sort()
                e1, l1 = dp(m, surv.index(i) + 1, surv.index(j) + 1)
                early = min(early, e1 + 1)
                latest = max(latest, l1 + 1)
            return (early, latest)
            
        return list(dp(n, firstPlayer, secondPlayer))
