from collections import deque
from typing import List

class Solution:
    def minCost(self, grid: List[List[int]]) -> int:
        m, n = len(grid), len(grid[0])
        directions = [(0, 1), (0, -1), (1, 0), (-1, 0)]  
        visited = [[False] * n for _ in range(m)]
        queue = deque([(0, 0, 0)]) 
        
        while queue:
            r, c, cost = queue.popleft()
            
            if visited[r][c]:
                continue
            visited[r][c] = True
            
            if (r, c) == (m - 1, n - 1):
                return cost

            for i, (dr, dc) in enumerate(directions):
                nr, nc = r + dr, c + dc
                if 0 <= nr < m and 0 <= nc < n and not visited[nr][nc]:
                    if grid[r][c] == i + 1:  
                        queue.appendleft((nr, nc, cost))
                    else:
                        queue.append((nr, nc, cost + 1))
        
        return -1 
