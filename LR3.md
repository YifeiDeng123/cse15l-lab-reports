# 1. Part 1 - Bugs
(1) A failure-inducing input for the buggy program
```
@Test 
public void testReverseInPlace1() {
    int[] input1 = { 3, 5, 7, 9, 11 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 11, 9, 7, 5, 3 }, input1);
}
```
(2) An input that doesn’t induce a failure
```
@Test 
public void testReverseInPlace2() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
}
```
(3) The symptom, as the output of running the tests
![Image](test.png) <br>
(4)
