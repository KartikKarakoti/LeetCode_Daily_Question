class Solution:
    def minimumOneBitOperations(self, n: int) -> int:
        def f(n):
            if n<=1: return n
            k=int(log2(n))
            return (1<<(k+1))-1-f(n^(1<<k))
        return f(n)
        
