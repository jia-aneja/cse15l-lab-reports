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

   ![Image](https://github.com/jia-aneja/cse15l-lab-reports/blob/main/Screenshot%202024-02-13%20at%205.39.42%20PM.png)

4. The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

   **CODE BEFORE:**

    ```
    static int[] reversed(int[] arr) {
        int[] newArray = new int[arr.length];
        for(int i = 0; i < arr.length; i += 1) {
          arr[i] = newArray[arr.length - i - 1];
        }
        return arr;
    }
    ```

   **CODE AFTER:**

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

   ![Image](Screenshot%202024-02-13%20at%205.11.46%20PM.png)

   ![Image](Screenshot%202024-02-13%20at%205.12.49%20PM.png)

   
2. `-type <type>`: searches for files of a particular type ('f' for files, 'd' for directories)

   ![Image](https://github.com/jia-aneja/cse15l-lab-reports/blob/main/Screenshot%202024-02-13%20at%205.21.25%20PM.png)

   ![Image](https://github.com/jia-aneja/cse15l-lab-reports/blob/main/Screenshot%202024-02-13%20at%205.21.41%20PM.png)

3. `-size [+|-]size[c]`: Search for files of a specific size. You can use + or - to specify larger or smaller sizes, and c to specify bytes explicitly.

   ![Image](https://github.com/jia-aneja/cse15l-lab-reports/blob/main/Screenshot%202024-02-13%20at%205.23.50%20PM.png)

   ![Image](https://github.com/jia-aneja/cse15l-lab-reports/blob/main/Screenshot%202024-02-13%20at%205.24.06%20PM.png)

4. `-mindepth <level>`: Start the search after a specific number of directory levels.

   ![Image](https://github.com/jia-aneja/cse15l-lab-reports/blob/main/Screenshot%202024-02-13%20at%205.25.04%20PM.png)

   ![Image](https://github.com/jia-aneja/cse15l-lab-reports/blob/main/Screenshot%202024-02-13%20at%205.25.11%20PM.png)

**SOURCES:**
- [Linux Manual Page](https://man7.org/linux/man-pages/man1/find.1.html)
- [Red Hat](https://www.redhat.com/sysadmin/linux-find-command)

***
