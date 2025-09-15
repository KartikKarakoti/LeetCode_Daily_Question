class Solution:
    def canBeTypedWords(self, text: str, brokenLetters: str) -> int:
        return sum(1 for w in text.split() if not any(c in brokenLetters for c in w))
