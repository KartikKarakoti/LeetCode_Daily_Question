class Solution:
    def mostPoints(self, q: List[List[int]]) -> int:
        n=len(q)
        @cache
        def dfs(i):
            if i>=n: return 0
            pt, skip=q[i]
            return max(pt+dfs(i+skip+1), dfs(i+1))
        return dfs(0)       
