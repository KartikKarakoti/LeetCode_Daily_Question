class Solution:
    def minZeroArray(self, nums: List[int], queries: List[List[int]]) -> int:
        n, m=len(nums), len(queries)
        freq=[0]*(n+1)
        op, k=0, 0
        for i in range(n):
            while op<nums[i]-freq[i]:
                if k>=m: 
                    return -1
                l, r, v=queries[k]
                if r<i:
                    k+=1 
                    continue
                freq[max(l, i)]+=v
                freq[r+1]-=v
                k+=1
            op+=freq[i]
        return k 
        
