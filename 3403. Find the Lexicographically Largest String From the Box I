class Solution:
    def answerString(self, word: str, nf: int) -> str:
        
        n = len(word)
        if nf == 1:
            return word

        couldbe = ''
        maxi= 'a'
        for i in range(n):
            if word[i] >= maxi:
                splits_left = (nf-i) if (nf-i)>=0 else 0
                couldbe = max(couldbe, word[i:n-splits_left+1])
                maxi = word[i]
            
        return couldbe
