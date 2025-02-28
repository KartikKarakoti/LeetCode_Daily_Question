class Solution:
    def shortestCommonSupersequence(self, str1: str, str2: str) -> str:
        m, n = len(str1), len(str2)
        dp = [[0] * (n + 1) for _ in range(m + 1)]

        for i in range(m + 1):
            for j in range(n + 1):
                if i == 0:
                    dp[i][j] = j
                elif j == 0:
                    dp[i][j] = i
                elif str1[i - 1] == str2[j - 1]:
                    dp[i][j] = 1 + dp[i - 1][j - 1]
                else:
                    dp[i][j] = 1  + min(dp[i - 1][j], dp[i][j - 1])
        
        i, j = m, n
        scs = []
        
        while i > 0 and j > 0:
            if str1[i - 1] == str2[j - 1]:  # Characters match
                scs.append(str1[i - 1])
                i -= 1
                j -= 1
            elif dp[i - 1][j] < dp[i][j - 1]:  # Take from str1
                scs.append(str1[i - 1])
                i -= 1
            else:  # Take from str2
                scs.append(str2[j - 1])
                j -= 1

        # Add remaining characters from str1 and str2
        while i > 0:
            scs.append(str1[i - 1])
            i -= 1
        while j > 0:
            scs.append(str2[j - 1])
            j -= 1

        return "".join(reversed(scs))
