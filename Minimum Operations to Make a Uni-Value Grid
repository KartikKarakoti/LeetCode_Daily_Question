class Solution:
    def minOperations(self, grid: List[List[int]], x: int) -> int:
        arr = [num for row in grid for num in row]  # Flatten the grid
        arr.sort()
        median = arr[len(arr) // 2]  # Find the median
        
        # Check if all elements can be transformed
        for num in arr:
            if (num - median) % x != 0:
                return -1  # Impossible case

        # Calculate the minimum number of operations
        return sum(abs(num - median) // x for num in arr)
