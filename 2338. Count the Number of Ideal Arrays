from collections import Counter
from math import comb

class Solution:
    def idealArrays(self, length: int, max_value: int) -> int:
        MOD = 1_000_000_007
        total_ways = max_value
        frequency_map = {num: 1 for num in range(1, max_value + 1)}
        
        for array_size in range(1, length): 
            new_frequency = Counter()
            for base_value in frequency_map: 
                for multiplier in range(2, max_value // base_value + 1): 
                    combinations = comb(length - 1, array_size)
                    total_ways += combinations * frequency_map[base_value]
                    new_frequency[multiplier * base_value] += frequency_map[base_value]
            frequency_map = new_frequency
            total_ways %= MOD
        
        return total_ways
