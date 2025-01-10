class Solution:
    def wordSubsets(self, words1: List[str], words2: List[str]) -> List[str]:
        maxf=[0]*26
        tem=[0]*26
        for word in words2:
            for w in word:
                tem[ord(w)-ord('a')]+=1
            for i in range(26):
                maxf[i]=max(maxf[i],tem[i])
            tem=[0]*26
        res=[]
        for word in words1:
            for w in word:
                tem[ord(w)-ord('a')]+=1
            flag=True
            for i in range(26):
                if maxf[i]>tem[i]:
                    flag=False
                    break
            if flag:
                res.append(word)
            tem=[0]*26
        return res
