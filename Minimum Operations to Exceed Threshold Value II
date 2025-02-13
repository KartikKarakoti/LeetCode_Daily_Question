class Solution:
    def minOperations(self, nums: List[int], k: int) -> int:
        heapq.heapify(nums) # turn nums into min heap
        operations = 0
        x = heapq.heappop(nums) # lowest num
        while x < k: # continue until lowest num >= k
            new_num = x * 2 + heapq.heappop(nums) # min(x,y) = x, max(x,y) = y
            x = heapq.heappushpop(nums, new_num) # add new num and pop lowest
            operations += 1

        return operations
