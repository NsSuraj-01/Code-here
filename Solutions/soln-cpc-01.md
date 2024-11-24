## 1. Trustworthy Subarrays
### Java
```java
import java.util.*;

public class Solution {
    public static int solve(int N, int[] Arr) {
        int count = 0;

        for (int i = 0; i < N; i++) {
            int min = Arr[i], max = Arr[i];

            for (int j = i; j < N; j++) {
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

    for i in range(N):
        min_val = Arr[i]
        max_val = Arr[i]

        for j in range(i, N):
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
---

## 2. Counting coordinates
### Java
```java
import java.util.Scanner;

public class RectanglePointCount {

    public static int countValidPoints(int x1, int y1, int x2, int y2, int xc, int yc, int R) {
        int count = 0;
        int R_squared = R * R; 

        for (int x = x1; x <= x2; x++) {
            for (int y = y1; y <= y2; y++) {
                // Check the distance condition
                if ((x - xc) * (x - xc) + (y - yc) * (y - yc) <= R_squared) {
                    count++;
                }
            }
        }

        return count;
    }

    public static void main(String[] args) {
        int result = countValidPoints(x1, y1, x2, y2, xc, yc, R);
        System.out.println(result);

        scanner.close();
    }
}
```

### Python
```python
def solve(x1, y1, x2, y2, xc, yc, R):
    count = 0

    for x in range(x1, x2 + 1):
        for y in range(y1, y2 + 1):
            # Calculate the Euclidean distance squared
            distance_squared = (x - xc) ** 2 + (y - yc) ** 2
            
            # Check if the distance is within the allowed range
            if distance_squared <= R ** 2:
                count += 1

    return count

# Rectangle coordinates: x1 = 1, y1 = 1, x2 = 4, y2 = 4
# Query point: xc = 2, yc = 2, R = 2
result = solve(1, 1, 4, 4, 2, 2, 2)
print(result)  # Example output

```
