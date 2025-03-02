class Solution:
    def mergeArrays(self, nums1: List[List[int]], nums2: List[List[int]]) -> List[List[int]]:
        n1, n2=len(nums1), len(nums2)
        ans=[]
        i, j=0, 0
        while i<n1 or j<n2:
            id1=2000 if i==n1 else nums1[i][0]
            id2=2000 if j==n2 else nums2[j][0]
            if id1==id2: 
                ans.append([id1, nums1[i][1]+nums2[j][1]])
                i+=1
                j+=1
            elif id1<id2: 
                ans.append(nums1[i])
                i+=1
            else:
                ans.append(nums2[j])
                j+=1
        return ans
        
