# Leetcode Solutions & Intuition 

## 1. Valid Anagram
### Intuition
Valid Anagrams have the same length and the same characters. 

### Approach
First we check if they are of the same length. False, they aren't anagrams. After confirming they have the same length, we create two dictionaries that have the characters present in each string and their counts. 

We use .get() for the counting process. s_char[s[n]] means that the count of the character n from s in s_char dictionary is incremented by 1.

### Complexity
- Time complexity:
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

### Code
```
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        s_char, t_char = {}, {}
        if len(s)!= len(t):
            return False
        for n in range(len(s)):
            s_char[s[n]] = 1 + s_char.get(s[n],0)
            t_char[t[n]] = 1 + t_char.get(t[n],0)
        for c in s_char:
            if s_char[c] != t_char.get(c, 0):
                return False
        return True     
        
```
## 2. Contains Duplicate
### Intuition
Check if there are repeating numbers in the list.

### Approach
First we create an empty set and as we iterate through the elements in nums, we add them to the set if they arent in the set already and if they are there already, it means that that is a duplicate value in which case it returns True. 

### Complexity
- Time complexity:
O(N)

- Space complexity:
O(N)

### Code
```
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        num_set = set()
        for i in nums:
            if i not in num_set:
                num_set.add(i)
            else:
                return True

        return False
```
## 3. Two Sum
### Intuition
If we find the difference between the target and each value we iterate through in the array, and check if the difference is in the array or not, we can find two sum that results into the target value.

### Approach
First we create an empty dictionary with the intention of storing the values and their positions. The we iterate through the arrays and calculate the difference between the target and the current number. If the different is in the dictionary, then the position of the two integers (one from the dictionary and another from the array) is returned, if now the value and its position in the array is stored in the dictionary. 

### Complexity
- Time complexity:
O(N)

- Space complexity:
O(N)

### Code
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        preMap = {}

        for i, n in enumerate(nums):
            diff = target - n
            if diff in preMap:
                return [preMap[diff], i]
            preMap[n] = i
        return        
```
## 4. Linked List Cycle
### Intuition
Floyd's Tortoise and Hare algorithm [ Linked List Cycle].


### Approach
We have two pointers: slow (shifted by 1) and fast(shifted by 2) pointers. 

### Complexity
- Time complexity:
O(n)

- Space complexity:
O(1)


### Code
```
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None

    class Solution:
        def hasCycle(self, head: Optional[ListNode]) -> bool:
            slow, fast = head, head

            while fast and fast.next:
                slow = slow.next
                fast = fast.next.next
                if slow == fast:
                    return True
            return False
        
```
## 5. Happy Number
### Intuition
Floyd's Tortoise and Hare algorithm [ Linked List Cycle].


### Approach
In the "isHappy" function, we have two pointers: slow (shifted by 1) and fast(shifted by 2) pointers. Therefore, before we the slow and the fast pointers meet, sumSquaredDigits is called twice on fast pointer and slow calls sumSquaredDigits once. Recursion continues till the fast pointer becomes equal to 1 and returns True, else, False is returned. 

The sumSquaredDigits function calculates the sum of the squares of the digits of a number. 
-It initializes output to 0, which will store the cumulative sum of the squared digits.
-It uses a while loop to iterate through each digit of the number:
-->(n % 10) extracts the last digit of n.
-->(n % 10) ** 2 calculates the square of the digit.
-->n = n // 10 removes the last digit from n.
The squared digit is added to the output.
The loop continues until n becomes 0, meaning all digits have been processed.
The final output is the sum of the squares of the digits.

### Complexity
- Time complexity:
O(lg N)

- Space complexity:
O(N)


### Code
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        visit = set() #O(N)

        while n not in visit:
            visit.add(n)
            n = self.sumOfSquares(n)

        if n ==1:
            return True
        return False

    def sumOfSquares(self, n: int): -> int
        output = 0

        while n:
            digit = n % 10
            digit = digit ** 2
            output += digit
            n = n//10

        return output
```
## 6. Top K Frequent Elements
### Intuition
Floyd's Tortoise and Hare algorithm [ Linked List Cycle].


### Approach
In the "isHappy" function, we have two pointers: slow (shifted by 1) and fast(shifted by 2) pointers. Therefore, before we the slow and the fast pointers meet, sumSquaredDigits is called twice on fast pointer and slow calls sumSquaredDigits once. Recursion continues till the fast pointer becomes equal to 1 and returns True, else, False is returned. 

The sumSquaredDigits function calculates the sum of the squares of the digits of a number. 
-It initializes output to 0, which will store the cumulative sum of the squared digits.
-It uses a while loop to iterate through each digit of the number:
-->(n % 10) extracts the last digit of n.
-->(n % 10) ** 2 calculates the square of the digit.
-->n = n // 10 removes the last digit from n.
The squared digit is added to the output.
The loop continues until n becomes 0, meaning all digits have been processed.
The final output is the sum of the squares of the digits.

### Complexity
- Time complexity:
O(lg N)

- Space complexity:
O(N)


### Code
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        visit = set() #O(N)

        while n not in visit:
            visit.add(n)
            n = self.sumOfSquares(n)

        if n ==1:
            return True
        return False

    def sumOfSquares(self, n: int): -> int
        output = 0

        while n:
            digit = n % 10
            digit = digit ** 2
            output += digit
            n = n//10

        return output
```

## 6. Destination City
### Intuition
Each city points to another city. If a city doesn't point to any other city, then that is the destination city.


### Approach
Th

### Complexity
- Time complexity:
O(lg N)

- Space complexity:
O(N)


### Code
```
## 6. Top K Frequent Elements
### Intuition
Floyd's Tortoise and Hare algorithm [ Linked List Cycle].


### Approach
In the "isHappy" function, we have two pointers: slow (shifted by 1) and fast(shifted by 2) pointers. Therefore, before we the slow and the fast pointers meet, sumSquaredDigits is called twice on fast pointer and slow calls sumSquaredDigits once. Recursion continues till the fast pointer becomes equal to 1 and returns True, else, False is returned. 

The sumSquaredDigits function calculates the sum of the squares of the digits of a number. 
-It initializes output to 0, which will store the cumulative sum of the squared digits.
-It uses a while loop to iterate through each digit of the number:
-->(n % 10) extracts the last digit of n.
-->(n % 10) ** 2 calculates the square of the digit.
-->n = n // 10 removes the last digit from n.
The squared digit is added to the output.
The loop continues until n becomes 0, meaning all digits have been processed.
The final output is the sum of the squares of the digits.

### Complexity
- Time complexity:
O(lg N)

- Space complexity:
O(N)


### Code
```
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        visit = set() #O(N)

        while n not in visit:
            visit.add(n)
            n = self.sumOfSquares(n)

        if n ==1:
            return True
        return False
```

