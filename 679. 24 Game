div = lambda x,y: reduce(truediv,(x,y)) if y else inf
ops = (add, sub, mul, div)

class Solution:
    def judgePoint24(self, cards: List[int]) -> bool:

        def dfs(c: list) -> bool:

            if len(c) <2 : return isclose(c[0], 24)
            
            for p in set(permutations(c)):
                for num in {reduce(op,p[:2]) for op in ops}:
                    if dfs([num] + list(p[2:])): return True

            return False        
        
        return dfs(cards)
