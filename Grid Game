class Solution:
    def gridGame(self, grid):
        top = sum(grid[0])
        bottom = 0
        res = float('inf')
        
        for i in range(len(grid[0])):
            top -= grid[0][i]
            res = min(res, max(top, bottom))
            bottom += grid[1][i]
        
        return res
