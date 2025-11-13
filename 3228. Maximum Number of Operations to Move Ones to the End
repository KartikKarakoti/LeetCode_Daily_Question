class Solution:
    def maxOperations(self, s: str) -> int:
        return sum(accumulate(map(len,findall('(1+)0',s))))
