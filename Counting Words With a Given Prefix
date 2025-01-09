class Solution:
    def prefixCount(self, words: list[str], pref: str) -> int:
        c = 0
        n = len(pref)
        for word in words:
            if len(word) >= n and word[:n] == pref:
                c += 1
        return c
