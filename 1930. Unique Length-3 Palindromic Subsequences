class Solution {
public:
    int countPalindromicSubsequence(string s) {
        map<char, int> firstOcc;
        map<char, int> lastOcc;

        // Record first and last occurrence
        for (int i = 0; i < (int)s.size(); i++) {
            lastOcc[s[i]] = i;
            if (firstOcc.find(s[i]) == firstOcc.end()) {
                firstOcc[s[i]] = i;
            }
        }

        int ans = 0;

        // For each possible outer character C
        for (auto [C, L] : firstOcc) {
            int R = lastOcc[C];
            set<char> middleChars;

            // Count distinct middle characters X between L and R
            for (int i = L + 1; i < R; i++) {
                middleChars.insert(s[i]);
            }

            ans += (int)middleChars.size();
        }

        return ans;
    }
};
