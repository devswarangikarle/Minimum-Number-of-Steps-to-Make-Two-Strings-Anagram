# Minimum-Number-of-Steps-to-Make-Two-Strings-Anagram
You are given two strings of the same length s and t. In one step you can choose any character of t and replace it with another character.  Return the minimum number of steps to make t an anagram of s.  An Anagram of a string is a string that contains the same characters with a different (or the same) ordering.   

from collections import Counter

class Solution:
    def minSteps(self, s, t):
        if len(s) != len(t):
            return -1  

        
        count_s = Counter(s)
        count_t = Counter(t)

     
        diff = count_t - count_s

        
        return sum(abs(diff[char]) for char in diff)

solution = Solution()
s1, t1 = "bab", "aba"
print(solution.minSteps(s1, t1))  
s2, t2 = "leetcode", "practice"
print(solution.minSteps(s2, t2))  

s3, t3 = "anagram", "mangaar"
print(solution.minSteps(s3, t3))  

