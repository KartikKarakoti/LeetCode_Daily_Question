class Solution:
    def checkValidCuts(self, n: int, rectangles: List[List[int]]) -> bool:
        def can_split(intervals: List[List[int]]) -> bool:
            intervals.sort()
            cuts = 0
            current_end = intervals[0][1]
            
            for start, end in intervals[1:]:
                if start >= current_end:
                    cuts += 1
                    if cuts >= 2:
                        return True
                current_end = max(current_end, end)
            
            return False

        x_intervals = [[x1, x2] for x1, _, x2, _ in rectangles]
        y_intervals = [[y1, y2] for _, y1, _, y2 in rectangles]

        return can_split(x_intervals) or can_split(y_intervals)
