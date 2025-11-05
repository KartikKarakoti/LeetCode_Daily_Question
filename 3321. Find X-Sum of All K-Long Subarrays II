class Solution:
    def findXSum(self, nums, k, x):
        freq = Counter()
        top = SortedList()
        rest = SortedList()
        top_sum = 0
        ans = []

        def balance():# keeps top and rest balanced
            nonlocal top_sum
            while len(top) < x and rest:
                f, v = rest.pop()
                top.add((f, v))
                top_sum += f * v
            while len(top) > x:
                f, v = top.pop(0)
                top_sum -= f * v
                rest.add((f, v))
            while rest and top and rest[-1] > top[0]:
                f1, v1 = rest.pop()
                f2, v2 = top.pop(0)
                top_sum += f1 * v1 - f2 * v2
                top.add((f1, v1))
                rest.add((f2, v2))

        def add(num):
            nonlocal top_sum
            old = (freq[num], num)
            if old in top:
                top.remove(old)
                top_sum -= old[0] * old[1]
            elif old in rest:
                rest.remove(old)
            freq[num] += 1
            new = (freq[num], num)
            rest.add(new)
            balance()

        def remove(num):
            nonlocal top_sum
            old = (freq[num], num)
            if old in top:
                top.remove(old)
                top_sum -= old[0] * old[1]
            else:
                rest.remove(old)
            freq[num] -= 1
            if freq[num] > 0:
                rest.add((freq[num], num))
            else:
                del freq[num]
            balance()

        for i in range(k):# initial window
            add(nums[i])
        ans.append(top_sum)

        for i in range(k, len(nums)):# slide the window
            remove(nums[i - k])
            add(nums[i])
            ans.append(top_sum)

        return ans
