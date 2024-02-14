# CSE 15L Lab Report 3

## Part 1 - BUGS 🪲

***

The `reversed` method of `ArrayExamples` class has a bug.



1. A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)
   ```
   @Test
   public void testReversedfail() {
     int[] input = {1, 2, 3};
     assertArrayEquals(new int[]{3, 2, 1}, ArrayExamples.reversed(input));
   }
   ```

2. An input that doesn't induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)

   ```
   @Test
    public void testReversed() {
      int[] input1 = { };
      assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
    }
   ```
3. The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)

4. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

   CODE BEFORE:

    ```
    static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length];
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = newArray[arr.length - i - 1];
        }
        return arr;
    }
    ```

   CODE AFTER:

   ```
   static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length];
        for(int i = 0; i < arr.length; i += 1) {
          newArray[i] = arr[arr.length - i - 1];
        }
        return newArray;
    }
   ```

***

## Part 2 - Researching Commands

`find` command

1. `-iname` "pattern" is similar to the `-name` pattern but is case insensitive.

    ![Image](Screenshot%202024-02-13%20142057.png)

3. `-type <type>`: searches for files of a particular type ('f' for files, 'd' for directories)

4. `-size [+|-]size[c]`: Search for files of a specific size. You can use + or - to specify larger or smaller sizes, and c to specify bytes explicitly.

5. `-mindepth <level>`: Start the search after a specific number of directory levels.
