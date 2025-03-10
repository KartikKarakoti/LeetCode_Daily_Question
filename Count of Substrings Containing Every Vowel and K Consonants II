class Solution:
    def countOfSubstrings(self, word: str, k: int) -> int:
        cnt_vowel = {'a':0, 'e':0, 'i':0, 'o':0, 'u':0}
        left, start, cnt_diff_vowel, ans = 0, 0, 0, 0
        for ch in word:
            if ch in cnt_vowel:
                cnt_vowel[ch] += 1
                if cnt_vowel[ch] == 1:
                    cnt_diff_vowel += 1
            else:
                k -= 1
                
            while k < 0 or cnt_diff_vowel == 5 and cnt_vowel.get(word[left], 0) > 1:
                ch_left = word[left]
                left += 1
                if ch_left in cnt_vowel:
                    cnt_vowel[ch_left] -= 1
                    if cnt_vowel[ch_left] == 0:
                        cnt_diff_vowel -= 1
                else:
                    k += 1  
                    start = left
                       
            if cnt_diff_vowel == 5 and k == 0:
                ans += left - start + 1
        return ans
