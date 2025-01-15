class Solution:
    def minimizeXor(self, num1: int, num2: int) -> int:
        diff_set_bits = num1.bit_count() - num2.bit_count()
        if diff_set_bits > 0:
            # Reset the 'diff_set_bits' least significant bits of the number 'num1'
            for _ in range(diff_set_bits):
                num1 &= num1 - 1
        else:
            # Set the 'diff_set_bits' least insignificant bits of the number 'num1'
            for _ in range(-diff_set_bits):  
                num1 |= num1 + 1   
        return num1
