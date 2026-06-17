Sqrt(x)

Problem

Given a non-negative integer x, return the square root of x rounded down to the nearest integer.

The returned integer should be the floor value of the square root.

You must not use any built-in exponent function or operator.

Approach

Use Binary Search to efficiently find the square root.

- Initialize two pointers:
  - left = 0
  - right = x

- Find the middle value (mid).
- Compare mid × mid with x:
  - If equal, return mid.
  - If smaller, search in the right half.
  - If larger, search in the left half.

- If an exact square root is not found, return right because it will contain the largest integer whose square is less than x.

Complexity

Time Complexity: O(log n)

Space Complexity: O(1)

Key Insight

Instead of checking every number from 1 to x, Binary Search repeatedly divides the search space in half.

This reduces the number of operations significantly and makes the solution very efficient.

Example

Input:
x = 4

Output:
2

Explanation:
2 × 2 = 4

Input:
x = 8

Output:
2

Explanation:
√8 = 2.828...

The integer part is 2.

Input:
x = 20

Output:
4

Explanation:
4 × 4 = 16
5 × 5 = 25

Since 25 > 20, the answer is 4.

Code

def mySqrt(x):
    left, right = 0, x

    while left <= right:
    
        mid = (left + right) // 2

        if mid * mid == x:
        
            return mid
            
        elif mid * mid < x:
        
            left = mid + 1
        else:
        
            right = mid - 1

    return right

