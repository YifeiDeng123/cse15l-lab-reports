# 1. Part 1 - Bugs
(1)
```
@Test 
	public void testReverseInPlace1() {
    int[] input1 = { 3, 5, 7, 9, 11 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 11, 9, 7, 5, 3 }, input1);
	}
```
