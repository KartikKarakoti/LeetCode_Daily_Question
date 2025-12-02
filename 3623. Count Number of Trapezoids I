class Solution:
    def countTrapezoids(self, points: List[List[int]]) -> int:
        mp = defaultdict(int)
        for x, y in points:
            mp[y] += 1
        
        y_lines_cnt = [n * (n - 1) // 2 for n in mp.values()]
        res = 0
        M = 10**9 + 7
        total = sum(y_lines_cnt)

        # Here we are calulating res += (p1 * p2) for every pair (p1, p2) in y_lines_cnt, in O(N) time.
        for s in y_lines_cnt:
            total -= s
            res += (s * total)

        return res % M
