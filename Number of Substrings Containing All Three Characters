class Solution:
    def numberOfSubstrings(self, s: str) -> int:
        n, cnt, letter, l=len(s), 0, 0, 0
        freq=[0]*3
        for r, c in enumerate(s):
            freq[ord(c)-97]+=1
            if freq[ord(c)-97]==1: letter+=1
            while letter==3:
                freq[ord(s[l])-97]-=1
                if freq[ord(s[l])-97]==0: letter-=1
                l+=1
            cnt+=l
        return cnt
