class Solution:
    def rangeAddQueries(self, n: int, queries: List[List[int]]) -> List[List[int]]:
        diff = [[0] * n for _ in range(n)]

        # diff array updates
        for row1, col1, row2, col2 in queries:
            for i in range(row1, row2 + 1):
                diff[i][col1] += 1
                if col2 + 1 < n:
                    diff[i][col2 + 1] -= 1

        # prefix sum row-wise
        for i in range(n):
            for j in range(1, n):
                diff[i][j] += diff[i][j - 1]

        return diff
