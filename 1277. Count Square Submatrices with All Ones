class Solution:
    def countSquares(self, grid: List[List[int]]) -> int:
        ans=0
        r=len(grid)
        c=len(grid[0])
        maxx=0
        for dig in range(c):
            ans += grid[0][dig]
        for dig in range(1,r):
            ans += grid[dig][0]
        for i in range(1,r):
            for j in range(1,c):
                if grid[i][j] == 1 and grid[i][j-1] > 0 and grid[i-1][j] > 0 and grid[i-1][j-1] > 0:
                    grid[i][j] += min(grid[i-1][j],grid[i][j-1],grid[i-1][j-1])
                ans += grid[i][j]
        return ans
