# Four-Divisors

Given an integer array nums, return the sum of divisors of the integers in that array that have exactly four divisors. If there is no such integer in the array, return 0.

class Solution:
    def get_divisors(self, n):

        divisors = []
        limit = n ** 0.5
        i = 1
        while(i <= limit):

            if(n % i == 0):
                divisors.append(i)
                
                poss_div = n//i
                if(poss_div != i):
                    divisors.append(poss_div)

            i += 1
        
        return divisors
    
    def sumFourDivisors(self, nums: list[int]) -> int:
        
        ans = 0
        for num in nums:
            divisors = self.get_divisors(num)

            if(len(divisors) == 4):
                ans += sum(divisors)
        
        return ans
        
