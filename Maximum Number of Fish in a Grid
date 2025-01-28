class Solution:
    def findMaxFish(self, grid: List[List[int]]) -> int:
        rows, cols = len(grid), len(grid[0])
        visited = set()

        def dfs(row, col):
            if row < 0 or row >= rows or col < 0 or col >= cols or grid[row][col] == 0 or (row, col) in visited:
                return 0
            
            visited.add((row, col))
            
            res = 0
            for direction in [(0, 1), (1, 0), (-1, 0), (0, -1)]:
                res += dfs(row + direction[0], col + direction[1])
            
            return res + grid[row][col]
        
        res = 0
        for i in range(rows):
            for j in range(cols):
                if grid[i][j] > 0 and (i, j) not in visited:
                    res = max(res, dfs(i, j))

        return res
