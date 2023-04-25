# Lab Report 2
## This lab report will contain three parts:
* String Server(unfinished)
* Bugs and Debugging
* Reflection on Learning

## Part 1: String Server(unfinished)
I enrolled in this class late, so I was mainly working on catching up and lab 1, I will make this part up by late submission.
Please give me some comments for the later parts, thank you!

## Part 2: Bugs and Debugging
In week 3, we debuged a program and I'll display some of my results below.(for ArrayExamples.java and ArrayTests.java)
1. A failure-inducing input for the buggy program
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
2. An input that doesn’t induce a failure
```
@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```
3. The symptom, as the output of running the tests

4. The bug, as the before-and-after code change required to fix it
Before
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
After
```
  static void reverseInPlace(int[] arr) {
    int temp;
    for(int i = 0; i < arr.length/2; i += 1) {
      temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
```
The changes allows the for-loop to loop through 1/2 length of the loop so that the loop won't double reverse the array(which makes no changes)
The changes also allow the index to be saved by temp so it won't be lost while swapping.

## Part 3

