# study-notes
Computer science study notes

# Binary Search

```java
int binarySearch(int[] array, int value) {
    int start = 0;
    int end = array.length - 1;

    while (start <= end) {
        int m = (start + end) / 2;
        if (array[m] == value)
            return m;
        else if (array[m] < value)
            left = m + 1;
        else
            right = m - 1;
    }

    return -1;
}
```
