class Solution(object):
    def firstCompleteIndex(self, arr, mat):
        """
        :type arr: List[int]
        :type mat: List[List[int]]
        :rtype: int
        """
        m = len(mat)
        n = len(mat[0])

        # Declare array frequency for Row and Column
        rowFeq = [0] * m
        colFeq = [0] * n

        # Set HashMap for the Matrix value corresponding row Index and column Index 
        map = {}
        for i in range(m):
            for j in range(n):
                map[mat[i][j]] = [i, j]
        
        # Traversing the "arr", painting the "mat" cell and increasing the "rowFeq" and "colFeq"
        for i in range(len(arr)):
            idx = map[arr[i]]
            r = idx[0]
            c = idx[1]

            rowFeq[r] += 1
            colFeq[c] += 1

            # rowFeq[r] will be equal of no. of columns
            # colFeq[c] will be equal of no. of rows
            if rowFeq[r] == n or colFeq[c] == m:
                return i

        return -1

        
