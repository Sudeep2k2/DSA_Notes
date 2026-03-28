# Two Pointer Algorithm

## Intuition:
The intuition behind the Two Pointer Algorithm is to use two indices (pointers) to traverse a data structure efficiently by reducing unnecessary iterations.

Instead of using nested loops (O(n²)), two pointers help solve problems in linear time (O(n)) by moving from different directions or at different speeds.

---

## Explanation:

### Algorithm:

- Initialize two pointers:
  - `left` → start of the array (index 0)
  - `right` → end of the array (index n-1)

- Iterate while `left < right`:
  - If condition is satisfied → process result
  - Else move pointers:
    - Increment `left` → move forward
    - Decrement `right` → move backward

- Stop when `left >= right`

---

## Explanation:

The algorithm works by narrowing down the search space:

- If the current condition requires a larger value → move `left` forward
- If the current condition requires a smaller value → move `right` backward
- Each step reduces the number of elements to check

This avoids re-checking elements and improves efficiency.

---

## Explanation of Correctness:

The algorithm works because:

- It eliminates unnecessary comparisons
- Each movement reduces the search space
- Every element is processed at most once

---

## Time Complexity:
- O(n)

## Space Complexity:
- O(1)

---

## Code (Example: Pair with Target Sum in Sorted Array)

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
