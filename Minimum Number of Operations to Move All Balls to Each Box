class Solution:
    def minOperations(self, boxes: str) -> List[int]:
        n=len(boxes)
        ans=[0]*n
        P=[]

        for i, x in enumerate(boxes):
            if x=='1':
                P.append(i)
                ans[0]+=i

        pz=len(P)
        L, R=0, pz
        j=0
        for i in range(1, n):
            if j<pz and i>P[j]:
                L+=1
                R-=1
                j+=1
            ans[i]=ans[i-1]+L-R
        return ans
