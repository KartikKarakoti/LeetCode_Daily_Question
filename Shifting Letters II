class Solution:
    def shiftingLetters(self, s: str, shifts: list[list[int]]) -> str:
        n = len(s)
        shift = [0] * (n + 1)

        for shiftOp in shifts:
            start, end, direction = shiftOp
            shift[start] += (1 if direction == 1 else -1)
            if end + 1 < n:
                shift[end + 1] -= (1 if direction == 1 else -1)

        currentShift = 0
        shiftList = list(s)
        for i in range(n):
            currentShift += shift[i]
            netShift = (currentShift % 26 + 26) % 26
            shiftList[i] = chr((ord(shiftList[i]) - ord('a') + netShift) % 26 + ord('a'))

        return ''.join(shiftList)
