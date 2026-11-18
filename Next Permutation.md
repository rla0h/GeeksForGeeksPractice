## 01. Next Permutation

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/next-permutation5226/1)

### Problem Description

**Task:** Given an array of integers arr[] representing a permutation, implement the next permutation that rearranges the numbers into the lexicographically smallest greater (or next) permutation. If no next permutation exists, rearrange the numbers into the lowest possible order (i.e., sorted in ascending order). Examples:Input: arr[] = [2, 4, 1, 7, 5, 0]

#### Examples

##### Example 1

- **Output:**
```text
[3, 4, 5, 1, 2]
```
- **Explanation:** The next permutation of the given array is [3, 4, 5, 1, 2].

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (C++)

- **Submitted:** 2026-11-18 06:38:54
- **Status:** Correct
- **Marks:** 4

```cpp
class Solution {
public:
    void nextPermutation(vector<int>& arr) {
        int n = static_cast<int>(arr.size());

        int find_left_index = n - 2;

        while (find_left_index >= 0 && arr[find_left_index] >= arr[find_left_index + 1]) {
            --find_left_index;
        }

        if (find_left_index < 0) {
            std::reverse(arr.begin(), arr.end());
            return;
        }

        int find_right_index = n - 1;

        while (arr[find_right_index] <= arr[find_left_index]) {
            --find_right_index;
        }


        std::swap(arr[find_left_index], arr[find_right_index]);

        std::reverse(arr.begin() + find_left_index + 1, arr.end());
    }
};
```

*Generated on: 2026. 11. 18. 오전 10:14:12*