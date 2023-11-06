# Lab 3 Report - Jake Kondo
---
## Part 1 - Bugs
---
### Fail-Inducing Input
```
  @Test
  public void testReversed() {
    int[] input1 = {8,9};
    assertArrayEquals(new int[]{9,8}, ArrayExamples.reversed(input1));
  }
```
### Input that does not induce a failure
```
  @Test
  public void testReversed() {
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
  }
```
### Symptoms of Fail-Inducing Input
```
  @Test
  public void testReversed() {
    int[] input1 = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input1));
  }

    @Test
  public void testReversed2() {
    int[] input1 = {8};
    assertArrayEquals(new int[]{8}, ArrayExamples.reversed(input1));
  }
```
<img width="979" alt="Screenshot 2023-11-05 at 8 50 39 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/35a553f6-b3d4-4d9c-8ac1-cdb98be92b74">

### Bug Fix Before and After

**Before**
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
**After**
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```
<img width="402" alt="Screenshot 2023-11-05 at 8 56 27 PM" src="https://github.com/jkondo14/cse15l-lab-reports/assets/146896972/c90a469e-dd92-47cd-b0f3-5bd0064c2b1d">
<br />
The original code changed each index of the original array with elements from newArray, which does not contain any element since it is a new Array, thus the code did not copy into the right array or copy it in reverse order into either array.
<br />
<br />
The new code copies the elements from the original array into newArray in reverse orders and returns newArray unlike the original code, where it returned the original array.
