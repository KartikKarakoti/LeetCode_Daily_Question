class Solution:
    def stringMatching(self, words: List[str]) -> List[str]:
        ans = set()
        for x in words:
            for y in words:
                if x != y and x in y:
                    ans.add(x)
        return list(ans)
