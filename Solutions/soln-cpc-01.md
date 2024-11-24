## 1. Trustworthy Subarrays
### Java
```java
import java.util.*;

public class Solution {
    public static int solve(int N, int[] Arr) {
        int count = 0;

        // Iterate over all starting points of the subarray
        for (int i = 0; i < N; i++) {
            int min = Arr[i], max = Arr[i];

            // Expand the subarray
            for (int j = i; j < N; j++) {
                // Update min and max for the current subarray
                min = Math.min(min, Arr[j]);
                max = Math.max(max, Arr[j]);

                // Calculate length of the current subarray
                int length = j - i + 1;

                // Check the "trustworthy" condition
                if ((min * max) % length == 0) {
                    count++;
                }
            }
        }

        return count;
    }

    public static void main(String[] args) {
        int N = 5;
        int[] Arr = {1, 2, 3, 4, 5};
        System.out.println(solve(N, Arr));
    }
}
```

### Python
```python
def solve(N, Arr):
    count = 0

    # Iterate over all starting points of the subarray
    for i in range(N):
        min_val = Arr[i]
        max_val = Arr[i]

        # Expand the subarray
        for j in range(i, N):
            # Update min and max for the current subarray
            min_val = min(min_val, Arr[j])
            max_val = max(max_val, Arr[j])

            # Calculate length of the current subarray
            length = j - i + 1

            # Check the "trustworthy" condition
            if (min_val * max_val) % length == 0:
                count += 1

    return count

if __name__ == "__main__":
    T = int(input("Enter number of test cases: "))
    for _ in range(T):
        N = int(input())
        Arr = list(map(int, input().split()))
        print(solve(N, Arr))
```
