class Solution:
    def findLexSmallestString(self, s: str, a: int, b: int) -> str:
        res,q = set(),deque([tuple(map(int,s))])
        while q:
            t = q.pop()
            for t in tuple((d+a)%10 for d,a in zip(t,cycle((0,a)))),t[-b:]+t[:-b]:
                if t not in res: res.add(t);q.append(t)
        
        return ''.join(map(str,min(res)))
