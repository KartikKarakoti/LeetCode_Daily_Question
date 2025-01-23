class Solution:
    def countServers(self, grid: List[List[int]]) -> int:
        Rows = [sum(row) for row in grid]
        Col = [sum(grid[i][j] for i in range(len(grid))) for j in range(len(grid[0]))]
        return sum(1 for i in range(len(grid)) for j in range(len(grid[0])) if grid[i][j] == 1 and (Rows[i] > 1 or Col[j] > 1))
