# CSE 15L
## Lab Report 5

**Part 1 - Debugging Scenario**

The repository I am using for this lab is from week 4.

https://github.com/ucsd-cse15l-f23/lab3

[lab3](https://github.com/ucsd-cse15l-f23/lab3)

Conversation on EdStem:

```
Student : I wrote this test for the reversed method in ArrayExamples.java, and I my test is failing. How can I fix it?
```

![Image](Screenshot%202024-03-11%20213836.png)

```
TA: As discussed during the Monday lecture of week 3 (https://ucsd-cse15l-w24.github.io/week3/index.html),
it's hard to help with questions that only provide symptoms without showing the code.
We need to see more (like the reversed method of ArrayExamples.java) in order to detect the bug.
You could also come to Office Hours to get help.
```

```
Student: I wrote the following code for the reversed method and this is the error message I am getting.
```
Code:
![Image](Screenshot%202024-03-11%20220050.png)

Bash Script:
![Image](Screenshot%202024-03-11%20220159.png)

Terminal Behavior:
![Image](Screenshot%202024-03-11%20220541.png)

```
TA: The bug is in the reversed method.
While appending the elements in reversed order, be careful about the list you are updating and returning.
```

```
Student: I noticed it! So basically in line 17, I accidentally switched the positions of arr and newArray.
And I should return newArray instead.
```

```
TA: Yes, that's right!
```

***

**Information about the setup:**

File and directory structure:

```
lab3 (directory)
  lib (directory)
  ArrayExamples.java
  ArrayTests.java
  FileExample.java
  LinkedListExample.java
  ListExamples.java
  test.sh
```
For this lab report, only ArrayExamples.java, ArrayTests.java and test.sh were used.

***

Content of ArrayExamples.java:
```
public class ArrayExamples {

  // Changes the input array to be in reversed order
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

  // Returns a *new* array with all the elements of the input array in reversed
  // order
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }

  // Averages the numbers in the array (takes the mean), but leaves out the
  // lowest number when calculating. Returns 0 if there are no elements or just
  // 1 element in the array
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }


}
```

Content of ArrayTests.java:
```
import static org.junit.Assert.*;
import org.junit.*;

public class ArrayTests {
	@Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}


  @Test
  public void testReversed1() {
    int[] input1 = { };
    assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
  }

  @Test
  public void testReversed2() {
    int[] input1 = {1, 2, 3};
    assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input1));
  }
}
```

Content of test.sh:
```
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ArrayTests
```

***

Command line:
`bash test.sh`

Terminal output:

```
JUnit version 4.13.2
...E
Time: 0.006
There was 1 failure:
1) testReversed2(ArrayTests)
arrays first differed at element [0]; expected:<3> but was:<0>
      at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:78)
      at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:28)
      at org.junit.Assert.internalArrayEquals(Assert.java:534)
      at org.junit.Assert.assertArrayEquals(Assert.java:418)
      at org.junit.Assert.assertArrayEquals(Assert.java:429)
      at ArrayTests.testReversed2(ArrayTests.java:22)
      ... 30 trimmed
Caused by: java.lang.AssertionError: expected:<3> but was:<0>
      at org.junit.Assert.fail(Assert.java:89)
      at org.junit.Assert.failNotEquals(Assert.java:835)
      at org.junit.Assert.assertEquals(Assert.java:120)
      at org.junit.Assert.assertEquals(Assert.java:146)
      at org.junit.internal.ExactComparisonCriteria.assertElementsEqual(ExactComparisonCriteria.java:8)
      at org.junit.internal.ComparisonCriteria.arrayEquals(ComparisonCriteria.java:76)
      ... 36 more

FAILURES!!!
Tests run: 3,  Failures: 1
```

***

Correct code of the reversed method after bug fix:

```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

We have to update the newArray by iterating arr in reverse order and return newArray not arr.

***

**PART 2: Reflection**

I learned how the autograder system works and how to build it. It was really cool and I loved working on it.

***
