class Solution:
    def partitionLabels(self, s: str) -> List[int]:
        letters = set()
        first = {}
        last = {}
        ranges = []
        for i in range(len(s)):
            letter = s[i]
            letters.add(letter)
            if letter not in first:
                first[letter] = i
                last[letter] = i
            else:
                last[letter] = i
        for letter in letters:
            ranges.append([first[letter], last[letter]])
        ranges.sort()
        merged = [ranges[0]]
        for r in ranges[1:]:
            start, end = merged[-1]
            new_start, new_end = r
            #if new_start >= start and new_end <= end do nothing
            if new_start < end:
                merged[-1] = [start, max(end, new_end)]
            else:
                merged.append(r)
        return [end - start + 1 for start, end in merged]
