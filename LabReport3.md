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

   ![Image](Screenshot%202024-02-13%20at%205.39.42%20PM.png)

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
   BUG FIX: Initially, the code was changing the elements in the original array `arr` itself by assigning the values from `newArray`. However, `newArray` is empty and should contain the reversed array (elements in reverse order). Hence, in the corrected code, we are appending elements in `newArray` from `arr` in reverse order.

***

## Part 2 - Researching Commands

`find` command

1. `-iname` "pattern" is similar to the `-name` pattern but is case insensitive.

   ```
   [user@sahara ~/docsearch/technical]$ find biomed/ -iname "1468*.txt"
   biomed/1468-6708-3-4.txt
   biomed/1468-6708-3-10.txt
   biomed/1468-6708-3-7.txt
   biomed/1468-6708-3-3.txt
   biomed/1468-6708-3-1.txt

   ```

   ```

   [user@sahara ~/docsearch/technical]$ find 911report/ -iname "Pre*.txt"
   911report/preface.txt

   ```

   
2. `-type <type>`: searches for files of a particular type ('f' for files, 'd' for directories)

   ```
   [user@sahara ~/docsearch/technical]$ find -type d
   .
   ./911report
   ./biomed
   ```

   ```
   [user@sahara ~/docsearch/technical]$ find 911report/ -type f
   911report/chapter-13.4.txt
   911report/chapter-2.txt
   911report/chapter-11.txt
   911report/chapter-13.1.txt
   911report/chapter-10.txt
   911report/chapter-3.txt
   911report/chapter-7.txt
   911report/preface.txt
   911report/chapter-5.txt
   911report/chapter-9.txt
   911report/chapter-8.txt
   911report/chapter-13.3.txt
   911report/chapter-1.txt
   911report/chapter-13.5.txt
   911report/chapter-13.2.txt
   911report/chapter-6.txt
   911report/chapter-12.txt
   ```

3. `-size [+|-]size[c]`: Search for files of a specific size. You can use + or - to specify larger or smaller sizes, and c to specify bytes explicitly.

   ```
   [user@sahara ~/docsearch/technical]$ find biomed/ -size +120 
   biomed/1472-6904-3-1.txt
   biomed/1471-2105-3-2.txt
   biomed/1471-2202-3-1.txt
   biomed/1475-4924-1-10.txt
   biomed/1472-6882-1-10.txt
   biomed/1471-2105-3-18.txt
   biomed/1472-6904-2-5.txt
   biomed/1471-2121-3-15.txt
   biomed/1472-6807-3-1.txt
   biomed/1471-2105-2-8.txt
   ```

   ```
   [user@sahara ~/docsearch/technical]$ find biomed/ -size +180
   biomed/1471-2105-3-2.txt
   ```

4. `-mindepth <level>`: Start the search after a specific number of directory levels.

   ```
   [user@sahara ~/docsearch/technical]$ find -mindepth 1 -type d
   ./911report
   ./biomed
   ```

   ```
   [user@sahara ~/docsearch/technical]$ find -mindepth 2 -type d
   [user@sahara ~/docsearch/technical]$
   ```

**SOURCES:**
- [Linux Manual Page](https://man7.org/linux/man-pages/man1/find.1.html) : for commands `-iname`, `-type` and `-mindepth`
- [Red Hat](https://www.redhat.com/sysadmin/linux-find-command) : for the `-size` command

***
