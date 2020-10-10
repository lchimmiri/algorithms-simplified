# algorithms-simplified
## 1) Kadane’s Algorithm

![Kadane’s image](https://github.com/lchimmiri/algorithms-simplified/blob/master/Kadane.PNG)

```
public int getMaxSubarraySumWithIndices(int[] array) {
		int currentMax = 0;
		int totalMax = Integer.MIN_VALUE;
		int startIndex = 0, endIndex = 0, tempIndex = 0;

		for (int i = 0; i < array.length; i++) {
			currentMax += array[i];

			if (currentMax < 0) {
				currentMax = 0;
				tempIndex = i + 1;
			} else if (totalMax < currentMax) {
				totalMax = currentMax;
				startIndex = tempIndex;
				endIndex = i;

			}
		}
		System.out.println("Start index: " + startIndex + " End index: " + endIndex);
		return totalMax;
	}
```
