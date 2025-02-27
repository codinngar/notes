
```java
public static void bubbleSort(int[] array, int size) {
	for (int i = 0; i < size - 1; i++) {
		boolean swapped = false;
		for (int j = 0; j < size - i - 1; j++) {
			if (array[j] > array[j + 1]) {
				swap(array[j], array[j + 1]);
				swapped = true;
			}
		}
		if (swapped == false)
			break;
	}
}
```