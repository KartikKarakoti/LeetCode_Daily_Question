class Solution:
    def trapRainWater(self, height: List[List[int]]) -> int:
        dir = (0, 1, 0, -1, 0)
        m, n = len(height), len(height[0])
        if m <= 2 or n <= 2:
            return 0

        boundary = []
        for i in range(m):
            boundary.append((height[i][0], i, 0))
            boundary.append((height[i][-1], i, n - 1))
            height[i][0] = height[i][-1] = -1

        for j in range(1, n - 1):
            boundary.append((height[0][j], 0, j))
            boundary.append((height[-1][j], m - 1, j))
            height[0][j] = height[-1][j] = -1

        heapify(boundary)
        ans, water_level = 0, 0

        while boundary:
            h, i, j = heappop(boundary)

            water_level = max(water_level, h)

            for a in range(4):
                i0, j0 = i + dir[a], j + dir[a + 1]
                if i0 < 0 or i0 >= m or j0 < 0 or j0 >= n or height[i0][j0] == -1:
                    continue
                currH = height[i0][j0]
                if currH < water_level:
                    ans += water_level - currH

                height[i0][j0] = -1
                heappush(boundary, (currH, i0, j0))
        return ans
 

        
