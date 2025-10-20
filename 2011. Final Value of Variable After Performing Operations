class Solution:
    def finalValueAfterOperations(self, operations: List[str]) -> int:
        count = 0
        for op in operations:
            if "-" in op:
                count -= 1
            else:
                count += 1
        return count
