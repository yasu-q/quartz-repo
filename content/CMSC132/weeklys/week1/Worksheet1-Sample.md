```java
package week1;

// Please do not duplicate this code for any purpose, or share it with anyone!

class Worksheet1
{
	private static void printArray(int[] arr)
	{
		for (int value : arr)
			System.out.print(value + " ");
		System.out.println();
	}
	
	// Try putting in your own code to see if it's correct!
	public static void main(String[] args)
	{
		// Test Cases for Problem 2
		int[] testArr2 = { 1, 3, 2, 6, 8, 4, 1 };
		System.out.println(findPos(testArr2, 3)); // Expect: 1
		System.out.println(findPos(testArr2, 2)); // Expect: 2
		System.out.println(findPos(testArr2, 1)); // Expect: 6
		System.out.println("-----");
		
		// Test Cases for Problem 3
		int[] testArr3 = { 1, 4, 3, 6, 5, 3, 2 };
		remove(testArr3, 1); // Expect: 4, 3, 6, 5, 3, 2, 0
		printArray(testArr3);
		
		remove(testArr3, 3); // Expect: 4, 6, 5, 3, 2, 0, 0
		printArray(testArr3);
		System.out.println("-----");
		
		// Test Cases for Problem 4
		int[] testArr4 = { 6, 2, 3, 8, 2 };
		insertAtFront(testArr4, 1); // Expect: 1, 6, 2, 3, 8
		printArray(testArr4);
		
		insertAtFront(testArr4, 3); // Expect: 3, 1, 6, 2, 3
		printArray(testArr4);
		
		insertAtFront(testArr4, 2); // Expect: 2, 3, 1, 6, 2
		printArray(testArr4);
	}
	
	static int findPos(int[] arr, int eltToFind)
	{
		int output = -1;
		
		for (int i = 0; i < arr.length; i++)
		{
			if (arr[i] == eltToFind)
				output = i;
		}
		
		return output;
	}
	
	static void remove(int[] arr, int toRemove)
	{
		int i = 0;
		boolean remove = false;
		
		// Find our element
		while (!remove && i < arr.length)
		{
			if (arr[i] == toRemove)
				remove = true;
			else
				i++;
		}
		
		// Shift all elements down
		while (i < arr.length)
		{
			int nextValue = 0;
			
			if (i + 1 < arr.length)
				nextValue = arr[i + 1];
			
			arr[i] = nextValue;
			i++;
		}
	}
	
	static void insertAtFront(int[] arr, int toAdd)
	{
		if (arr.length != 0)
		{
			// Note the i > 0, why not i >= 0?
			for (int i = arr.length - 1; i > 0; i--)
				arr[i] = arr[i - 1];
			
			arr[0] = toAdd;
		}
	}
}
```