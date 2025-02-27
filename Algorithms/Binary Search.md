# Notes
- array must be sorted

---

```java
public static void binarySearch(int[] array, int size, int target) {
	int l = 0;
	int r = size - 1;

	while (l <= r) {
		int m = (l + r) / 2;

		if (array[m] == target) {
			System.out.println("found at index " + m);
			return;
		}
		else if (array[m] > target)
			r = m - 1;
		else if (array[m] < target)
			l = m + 1;	
	}
	
	System.out.println("not found");
}
```