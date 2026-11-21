## 01. Sum of Subarrays

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/sum-of-subarrays2229/1)

### Problem Description

**Task:** Given an array arr[], find the sum of all the subarrays of the given array.Note: It is guaranteed that the total sum will fit within a 32-bit integer range.Examples:Input: arr[] = [1, 2, 3] Output: 20

#### Examples

##### Example 1

- **Output:**
```text
8Explanation: All subarray sums are: [1] = 1, [3] = 3, [1, 3] = 4. Thus total sum is 1 + 3 + 4 = 8.
```
- **Explanation:** All subarray sums are: [1] = 1, [2] = 2, [3] = 3, [1, 2] = 3, [2, 3] = 5, [1, 2, 3] = 6. Thus total sum is 1 + 2 + 3 + 3 + 5 + 6 = 20.Input: arr[] = [1, 3]

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-11-21 21:51:04
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
  public:
    int subarraySum(vector<int>& arr) {
        // code here
        int sum = 0;
        for (int i = 0; i < arr.size(); i++)
        {
            sum += arr[i] * (i + 1) * (arr.size() - i);
        }
        return sum;
    }
};
```

*Generated on: 2026. 11. 22. 오전 1:31:27*