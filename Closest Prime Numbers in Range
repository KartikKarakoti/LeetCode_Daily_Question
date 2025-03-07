class Solution:
        
    def closestPrimes(self, left: int, right: int) -> List[int]:
        def primeFind(val: int)->bool:
            if val==1: return False
            elif val==2: return True

            for i in range(2, int(val**0.5)+1):
                if val%i==0:
                    return False
            return True

        res=[-1,-1]
        prime=[]

        for p in range(left, right+1):
            if primeFind(p):
                # if prime like [2,3], [5,7], [11,13], [17,19] and so on ... found return immediately
                if len(prime)>=1 and p<=prime[len(prime)-1]+2:
                    return [prime[len(prime)-1], p]
                prime.append(p)
        

        if len(prime)<2:
            return res

        minVal=sys.maxsize
        for i in range(1, len(prime)):
            if minVal>prime[i]-prime[i-1]:
                minVal=prime[i]-prime[i-1]
                res=[prime[i-1], prime[i]] 

        return res


        
