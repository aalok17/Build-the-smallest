# Build-the-smallest
Problem of Day (10-dec-2022)(GFG)

```
class Solution:

    def buildLowestNumber(self, S,N):
        stack = []
        
        for num in S:
            while N and stack and stack[-1] > num:
                stack.pop()
                N -= 1
            stack.append(num)
        final = ''.join(stack[:len(stack) - N]).lstrip('0')
        
        return "0" if not final else final
