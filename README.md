class Solution(object):
    def mySqrt(self, x):
        """
        :type x: int
        :rtype: int
        """
        if x < 2:
            return x  # For 0 and 1, the square root is the number itself
        
        left, right = 2, x // 2  # We know sqrt(x) is between 2 and x//2 for x >= 2
        
        while left <= right:
            mid = (left + right) // 2
            guess = mid * mid
            
            if guess == x:
                return mid
            elif guess < x:
                left = mid + 1
            else:
                right = mid - 1
        
        return right
        
