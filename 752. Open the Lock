from queue import deque
class Solution:

    def openLock(self, deadends: List[str], target: str) -> int:
        queue = deque()
        
        deadends = set(deadends)
        if "0000" not in deadends:
            deadends.add("0000")
            queue.append(("0000", 0))
        while queue:
            curr_combination, moves = queue.popleft()
            if curr_combination == target:
                return moves
            
            for i in range(4):
                # move wheel at indx forward
                new_combination = curr_combination[:i] + str((int(curr_combination[i])+1)%10) + curr_combination[i+1:]
                if new_combination not in deadends:
                    deadends.add(new_combination)
                    queue.append((new_combination, moves+1))
                # move wheel at indx backward
                new_combination = curr_combination[:i] + str((int(curr_combination[i])-1)%10) + curr_combination[i+1:]
                if new_combination not in deadends:
                    deadends.add(new_combination)
                    queue.append((new_combination, moves+1))
        return -1




            





        
