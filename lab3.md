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
Code before fix
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
        arr[i] = arr[arr.length - i - 1];
    }
}
```
Code after fix
```
static void reverseInPlace(int[] arr) {
    int[] newArr = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
        newArr[i] = arr[arr.length - i - 1];
    }
    for(int j = 0; j < arr.length; j += 1) {
        arr[j] = newArr[j];
    }
}
```

