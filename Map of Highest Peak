class Solution:
    def highestPeak(self, isWater: List[List[int]]) -> List[List[int]]:
        r, c = len(isWater), len(isWater[0])
        d = (0, 1, 0, -1, 0)
        H = [[-1] * c for _ in range(r)]
        q = deque()
        for i, row in enumerate(isWater):
            for j, x in enumerate(row):
                if x == 1:
                    H[i][j] = 0
                    q.append((i, j))
        h = 0
        while q:
            qz = len(q)
            for a in range(qz):
                i, j = q.popleft()
                for b in range(4):
                    s, t = i + d[b], j + d[b + 1]
                    if s < 0 or s >= r or t < 0 or t >= c or H[s][t] != -1:
                        continue
                    q.append((s, t))
                    H[s][t] = h + 1
            h += 1
        return H

        
