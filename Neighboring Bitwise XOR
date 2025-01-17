class Solution:
    def doesValidArrayExist(self, derived: List[int]) -> bool:
        for start in [0, 1]:
            xor = start
            for i in derived:
                xor = xor ^ i
            if xor == start:
                return True
        return False
        
