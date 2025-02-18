class Solution:
    def smallestNumber(self, pattern: str) -> str:
        stack = ['', '1']  # Initialize stack with a base and the first number
        prev = pattern[0]  # Track the previous pattern ('D' or 'I')
        
        # Iterate through pattern with numbers starting from 2
        for num, i in enumerate(pattern + 'S', 2):  # Add sentinel 'S' to handle the last segment
            if i != prev:  # When the pattern changes
                if prev == 'D':  # Process the 'D' segment by reversing it
                    stack[-2] = stack[-2][:-1] + stack[-1][::-1]
                else:  # Process the 'I' segment as-is
                    stack[-2] = stack[-2][:-1] + stack[-1]
                
                # Start a new segment
                stack[-1] = stack[-2][-1] + str(num)
                prev = i
            else:  # Continue the current segment
                stack[-1] += str(num)
        
        return stack[0]  # The result is the first element in the stack
