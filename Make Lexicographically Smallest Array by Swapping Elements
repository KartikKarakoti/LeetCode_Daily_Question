class Solution:
    def lexicographicallySmallestArray(self, nums: List[int], limit: int) -> List[int]:
        n = len(nums)
        # Pair each number with its index and sort by the number
        sorted_enum = sorted((num, i) for i, num in enumerate(nums))
        
        new_positions = []
        curr_positions = []
        prev = float('-inf')
        
        for num, idx in sorted_enum:
            # If the current number exceeds the previous number by more than the limit,
            # sort and append the current positions to the result
            if num > prev + limit:
                new_positions.extend(sorted(curr_positions))
                curr_positions = [idx]
            else:
                curr_positions.append(idx)
            prev = num
        
        # Append any remaining positions
        new_positions.extend(sorted(curr_positions))
        
        # Construct the result array using the new positions
        res = [0] * n
        for i, idx in enumerate(new_positions):
            res[idx] = sorted_enum[i][0]
        
        return res
