class Solution:
    def findLucky(self, arr: list[int]) -> int:

        d = defaultdict(int)
        for num in arr: d[num]+= 1

        return max(filter(lambda x: d[x] == x, d), default = -1)
