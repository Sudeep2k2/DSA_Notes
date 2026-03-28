# Intuition:
The intuition behind the Two Pointer Algorithm is based on the idea that instead of checking all possible pairs (which takes O(n²)), we can use two pointers to intelligently reduce the search space and find the solution in a single pass.

By moving the pointers based on certain conditions, we eliminate unnecessary comparisons and reach the result efficiently.

# Explanation:

## Algorithm:

- Initialize two pointers:
  - left at the beginning (index 0)
  - right at the end (index n-1)

- Iterate while left < right:
  a. Check the condition based on the problem (e.g., sum, comparison, etc.)  
  b. If the condition is satisfied, return or store the result  
  c. If the current state is less than required, move left pointer forward  
  d. If the current state is greater than required, move right pointer backward  

- Continue this process until left >= right

## Explanation:

The algorithm starts by placing two pointers at opposite ends of the array.

As it iterates, it evaluates the condition using the elements at both pointers:

a. If the current elements satisfy the condition (for example, their sum equals the target), the solution is found.  

b. If the result is smaller than required, it means we need a larger value. Since the array is sorted, we move the left pointer forward to increase the value.  

c. If the result is greater than required, it means we need a smaller value. So, we move the right pointer backward to decrease the value.  

Each movement helps in reducing the number of elements to be checked, effectively shrinking the search space.

The algorithm continues this process until both pointers meet.

# Explanation of Correctness:

The algorithm works on the basis that the array is sorted.

This property guarantees that:

- Moving the left pointer forward increases the value  
- Moving the right pointer backward decreases the value  

This ensures that no possible valid pair is skipped, and every step moves closer to the solution.

Let's consider two cases:

## If a valid pair exists:

The pointers will eventually meet at the correct pair because the search space is reduced systematically based on comparisons.

## If no valid pair exists:

The pointers will cross each other, indicating that all possible pairs have been checked.

In both cases, the algorithm correctly determines the result.

The time complexity of the Two Pointer Algorithm is O(n) since each element is visited at most once.

This approach is efficient compared to nested loops as it avoids redundant comparisons and utilizes the sorted nature of the array.

# Code

```java
class Solution {
    public boolean hasPairWithSum(int[] nums, int target) {
        int left = 0;
        int right = nums.length - 1;
        
        while (left < right) {
            int sum = nums[left] + nums[right];
            
            if (sum == target) {
                return true;
            } else if (sum < target) {
                left++;
            } else {
                right--;
            }
        }
        
        return false;
    }
}
