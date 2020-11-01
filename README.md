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
## 2) Floyd’s cycle detection algorithm
<pre> 
Floyd's cycle-finding algorithm is a pointer algorithm that uses only two pointers, which move through the sequence at different speeds.
It is also called the "tortoise and the hare algorithm"
</pre>

```
public static <T> boolean detectLoop(SinglyLinkedList<T> list) {
		SinglyLinkedList<T>.Node slow = list.getHeadNode();
		SinglyLinkedList<T>.Node fast = list.getHeadNode();

		while (slow != null && fast != null && fast.nextNode != null) {
			slow = slow.nextNode; // the slow pointer will jump 1 step
			fast = fast.nextNode.nextNode; // the fast pointer will jump 2 steps
			// when the pointers become equal then there must be a loop
			if (slow == fast) {
				return true;
			}
		}
		return false;
	}
```
