class Solution:
    def maxAverageRatio(self, classes: List[List[int]], extraStudents: int) -> float:
        # Function to calculate the gain in pass ratio for adding a student to a class
        def pass_ratio_gain(passi, totali):
            return (passi + 1) / (totali + 1) - passi / totali
        
        # Max-heap to store the gain, -gain because heapq is a min-heap by default
        heap = []
        for passi, totali in classes:
            gain = pass_ratio_gain(passi, totali)
            heappush(heap, (-gain, passi, totali))
        
        # Distribute the extra students
        for _ in range(extraStudents):
            # Pop the class with the maximum gain
            gain, passi, totali = heappop(heap)
            # Add one student to this class
            passi += 1
            totali += 1
            # Recalculate gain and push back into heap
            new_gain = pass_ratio_gain(passi, totali)
            heappush(heap, (-new_gain, passi, totali))
        
        # Calculate the final average pass ratio
        total_ratio = 0
        for _, passi, totali in heap:
            total_ratio += passi / totali
        
        return total_ratio / len(classes)
