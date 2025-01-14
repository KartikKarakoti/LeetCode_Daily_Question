class Solution:
    def findThePrefixCommonArray(self, A: List[int], B: List[int]) -> List[int]:
        n = len(A)
        seen = set()
        C = [0] * n
        commonCount = 0
        for i in range(n):
            if A[i] in seen: commonCount += 1
            else: seen.add(A[i])
            if B[i] in seen: commonCount += 1
            else: seen.add(B[i])
            C[i] = commonCount
        return C
