## Summation of all triplets

```java
    public int build(int arr[], int node, int left, int right) {
        if(left == right) {
            return tree[node] = arr[left];
        }

        else {
            int mid = (left + right) >> 1;
            int li = 2 * node + 1;
            int ri = 2 * node + 2;

            build(arr, li, left, mid);
            build(arr, ri, mid+1, right);

            tree[node] = tree[li] + tree[ri];
            return tree[node];
        }
    }

    private void update(int node, int left, int right, int index, int val) {
        if(index < left || index > right) return;

        tree[node] += val;

        if(left != right) {
            int mid = (left + right) >> 1;
            update(2*node+1, left, mid, index, val);
            update(2*node+2, mid+1, right, index, val);
        }
    }

    public void update(int arr[], int idx, int val) {
        int rem = val - arr[idx];
        arr[idx] = val;
        update(0, 0, arr.length-1, idx, rem);
    }

    private int query(int node, int left, int right, int qi, int qj) {
        if(right < qi || qj < left) return 0;

        if(qi <= left && right <= qj) return tree[node];
        else {
            int mid = (left + right) >> 1;
            int lsum = query(2*node+1, left, mid, qi, qj);
            int rsum = query(2*node+2, mid+1, right, qi, qj);
            return lsum + rsum;
        }
    }

    // get sum from (qi, qj)
    public void query(int arr[], int qi, int qj) {
        int sum = query(0, 0, arr.length-1, qi, qj);
        System.out.println("sum: " + sum);
    }
}

// 1. find summation of all triplets
public static int summationOfTrips(int arr[], int queries[][]) {
    int n = arr.length;
    STree ds = new STree(arr);

    for(int q[] : queries) {
        int i=q[1]-1, j = q[2]-1, key = q[3];
        if(q[0] == 1) {
            for(int id=i; id <= j; id++) {
                ds.update(arr, id, arr[id] + key);
            }
        }
        else if(q[0] == 2) {
            for(int id=i; id <= j; id++) {
                ds.update(arr, id, arr[id] - key);
            }
        }
    }

    // Use sorting for optimised triplets summation
    int sum = 0;
    for (int i = 0; i < n - 2; i++) {
        for (int j = i + 1; j < n - 1; j++) {
            for (int k = j + 1; k < n; k++) {
                sum += arr[i] + arr[j] + arr[k];
            }
        }
    }

    return sum;
}

public static void main(String[] args) {
    int[] arr = {1, 2, 3, 4, 5};
    int[][] queries = {
        {1,1,3,2},
        {2,2,4,1},
        {1,4,5,3}
    };
    System.out.println(summationOfTrips(arr, queries));
}

```
```python
class SegmentTree:
    def __init__(self, arr):
        self.n = len(arr)
        self.tree = [0] * (4 * self.n)
        self.build(arr, 0, 0, self.n - 1)

    def build(self, arr, node, left, right):
        if left == right:
            self.tree[node] = arr[left]
            return self.tree[node]
        mid = (left + right) // 2
        li = 2 * node + 1
        ri = 2 * node + 2
        self.build(arr, li, left, mid)
        self.build(arr, ri, mid + 1, right)
        self.tree[node] = self.tree[li] + self.tree[ri]
        return self.tree[node]

    def update(self, node, left, right, index, val):
        if index < left or index > right:
            return
        self.tree[node] += val
        if left != right:
            mid = (left + right) // 2
            self.update(2 * node + 1, left, mid, index, val)
            self.update(2 * node + 2, mid + 1, right, index, val)

    def update_value(self, arr, idx, val):
        rem = val - arr[idx]
        arr[idx] = val
        self.update(0, 0, len(arr) - 1, idx, rem)

    def query(self, node, left, right, qi, qj):
        if right < qi or qj < left:
            return 0
        if qi <= left and right <= qj:
            return self.tree[node]
        mid = (left + right) // 2
        lsum = self.query(2 * node + 1, left, mid, qi, qj)
        rsum = self.query(2 * node + 2, mid + 1, right, qi, qj)
        return lsum + rsum

    def query_sum(self, arr, qi, qj):
        return self.query(0, 0, len(arr) - 1, qi, qj)


def summation_of_trips(arr, queries):
    n = len(arr)
    stree = SegmentTree(arr)

    for q in queries:
        i, j, key = q[1] - 1, q[2] - 1, q[3]
        if q[0] == 1:
            for id in range(i, j + 1):
                stree.update_value(arr, id, arr[id] + key)
        elif q[0] == 2:
            for id in range(i, j + 1):
                stree.update_value(arr, id, arr[id] - key)
    # Use sorting for optimised triplets summation
    total_sum = 0
    for i in range(n - 2):
        for j in range(i + 1, n - 1):
            for k in range(j + 1, n):
                total_sum += arr[i] + arr[j] + arr[k]

    return total_sum


if __name__ == "__main__":
    arr = [1, 2, 3, 4, 5]
    queries = [
        [1, 1, 3, 2],
        [2, 2, 4, 1],
        [1, 4, 5, 3]
    ]
    print(summation_of_trips(arr, queries))
```
