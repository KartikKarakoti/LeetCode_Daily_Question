class PrefSuffTrieNode:
    def __init__(self):
        self.children = {}
        self.poss_ends = 0

class PrefSuffTrie:
    def __init__(self):
        self.root = PrefSuffTrieNode()

    def insert(self, word):
        cur = self.root
        for i in range(len(word)):
            pr = word[i]
            su = word[len(word) - 1 - i]
            if (pr, su) not in cur.children:
                cur.children[(pr, su)] = PrefSuffTrieNode()
            cur = cur.children[(pr, su)]
            cur.poss_ends += 1

    def search(self, word):
        cur = self.root
        for i in range(len(word)):
            pr = word[i]
            su = word[len(word) - 1 - i]
            if (pr, su) not in cur.children:
                return 0
            cur = cur.children[(pr, su)]
        return cur.poss_ends 


class Solution:
    def countPrefixSuffixPairs(self, words: List[str]) -> int:
        res = 0
        trie = PrefSuffTrie()
        
        for word in words[::-1]:
            res += trie.search(word)
            trie.insert(word)
          
        return res
