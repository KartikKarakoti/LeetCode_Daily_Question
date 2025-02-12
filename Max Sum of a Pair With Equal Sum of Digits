class Solution:
    def maximumSum(self, nums: List[int]) -> int:
        def digitSum(x):
            sum=0
            while x>0:
                q, r=divmod(x, 10)
                sum+=r
                x=q
            return sum

        maxD=[0]*82
        ans=-1
        for x in nums:
            D=digitSum(x)
            if maxD[D]>0:
                ans=max(ans, maxD[D]+x)
            maxD[D]=max(maxD[D], x)
        return ans
        
        
