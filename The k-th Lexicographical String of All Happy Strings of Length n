class Solution:
    def getHappyString(self, n: int, k: int) -> str:
        count = 0 # tracks number of completed strings made

        def backtrack(i, happy_str):
            nonlocal count

            if i == n: 
                count += 1 # finished a string
                if count == k: 
                    return happy_str # found k string
                return None # wasn't k string
                
            for char in "abc": # a,b,c ensures lexicographical order
                if happy_str and happy_str[-1] == char: continue # prev char can't equal current

                res = backtrack(i + 1, happy_str + char) # add char and made rest of str
                if res:
                    return res # found k string

            return None # never found k string
            
        return backtrack(0, "") or "" # return k string or "" if never found
