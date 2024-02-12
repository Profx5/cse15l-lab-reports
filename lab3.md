Failure inducing input
```
int[] input2 = { 3, 2, 1 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 1, 2, 3 }, input1);
```
Input that doesn't induce failure
```
int[] input1 = { 3 };
ArrayExamples.reverseInPlace(input1);
assertArrayEquals(new int[]{ 3 }, input1);
```
