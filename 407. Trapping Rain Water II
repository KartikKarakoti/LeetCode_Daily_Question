class Solution:
    def trapRainWater(self, heightMap: List[List[int]]) -> int:
        if not heightMap or not heightMap[0]:
            return 0
        
        m, n = len(heightMap), len(heightMap[0])
        max_h = max(max(row) for row in heightMap)
        
        buckets = [deque() for _ in range(max_h + 1)]
        
        for i in range(m):
            for j in range(n):
                if i in (0, m-1) or j in (0, n-1):
                    buckets[heightMap[i][j]].append((i, j))
                    heightMap[i][j] = -1 
        
        trapped = 0
        curr_height = 0
        dirs = [(1,0),(-1,0),(0,1),(0,-1)]
        
        for h in range(max_h + 1):
            while buckets[h]:
                x, y = buckets[h].popleft()
                curr_height = max(curr_height, h)
                
                for dx, dy in dirs:
                    nx, ny = x + dx, y + dy
                    if 0 <= nx < m and 0 <= ny < n and heightMap[nx][ny] != -1:
                        nh = heightMap[nx][ny]
                        if nh < curr_height:
                            trapped += curr_height - nh
                        buckets[max(nh, curr_height)].append((nx, ny))
                        heightMap[nx][ny] = -1 
        
        return trapped
