# Intuition:
The intuition behind the Sliding Window Algorithm is based on maintaining a range (window) of elements and adjusting it dynamically instead of recomputing results for every possible subarray.

Instead of checking all subarrays (which takes O(n²)), we expand and shrink a window to efficiently process only relevant elements.

This allows us to reuse previous computations and avoid redundant work.

# Explanation:

## Algorithm:

- Initialize two pointers:
  - left at the beginning (index 0)
  - right at the beginning (index 0)

- Initialize a data structure (optional, based on problem):
  - sum / set / map / counter

- Iterate while right < n:

  a. Expand the window:
     - Include element at right into the window  
     - Update the data structure accordingly  

  b. Check condition:
     - If the condition is satisfied, update result  

  c. Shrink the window (if needed):
     - While the condition is violated:
       - Remove element at left from the window  
       - Move left forward  

  d. Move right forward  

- Continue until the entire array is processed

## Explanation:

The algorithm maintains a window defined by two pointers: left and right.

- The right pointer expands the window by including new elements  
- The left pointer shrinks the window when constraints are violated  

At each step:

a. We update the current state (sum, frequency, etc.)  

b. Check if the window satisfies the problem condition  

c. Adjust the window accordingly by moving left or right  

This avoids recomputing values for every subarray and ensures efficiency.

# Explanation of Correctness:

The algorithm works because it ensures that:

- Every element enters the window at most once  
- Every element leaves the window at most once  

This guarantees that all valid subarrays/windows are considered without redundant checks.

Let's consider two cases:

## If a valid window exists:

The window will eventually expand and adjust to include the valid subarray, and the condition check will capture it.

## If no valid window exists:

The window will expand and shrink across the entire array without satisfying the condition, correctly returning the result.

In both cases, the algorithm efficiently determines the result.

# Types of Sliding Window:

## 1. Fixed Size Window
- Window size remains constant (e.g., size = k)  
- Example: Maximum sum of subarray of size k  

## 2. Variable Size Window
- Window expands and shrinks dynamically  
- Example: Longest substring without repeating characters  

# Time Complexity:

The time complexity of the Sliding Window Algorithm is O(n) since each element is processed at most twice (once when added and once when removed).

This approach is efficient compared to nested loops as it avoids redundant computations and dynamically adjusts the window.

# Code

```java
class Solution {
    public int maxSumSubarray(int[] nums, int k) {
        int left = 0;
        int sum = 0;
        int maxSum = 0;

        for (int right = 0; right < nums.length; right++) {
            sum += nums[right];

            while (right - left + 1 > k) {
                sum -= nums[left];
                left++;
            }

            if (right - left + 1 == k) {
                maxSum = Math.max(maxSum, sum);
            }
        }

        return maxSum;
    }
}
```

# Key Differences from Two Pointers:

| Feature            | Two Pointers                  | Sliding Window                     |
|------------------|-------------------------------|-----------------------------------|
| Use case         | Pair problems (sorted arrays) | Subarrays / substrings            |
| Movement         | Based on comparison           | Expand + shrink window            |
| Data tracking    | Minimal                       | Requires extra structure (often)  |
| Typical problems | Two Sum II                    | Longest substring, max sum, etc.  |

# Final Takeaway:

- Two pointers → search between two ends  
- Sliding window → maintain a dynamic range  

If the problem involves:
- Subarrays / substrings  
- Constraints like size, sum, or uniqueness  

Then Sliding Window is the preferred approach.
