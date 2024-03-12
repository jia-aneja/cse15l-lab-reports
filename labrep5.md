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
TA: As discussed during the Monday lecture of week 3 (https://ucsd-cse15l-w24.github.io/week3/index.html) , it's hard to help with questions that only provide symptoms without showing the code. We need to see more (like the reversed method of ArrayExamples.java) in order to detect the bug. You could also come to Office Hours to get help.
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
TA: The bug is in the reversed method. While appending the elements in reversed order, be careful about the list you are updating.
```

```
Student: I noticed it! So basically in line 17, I accidentally switched the positions of arr and newArray.
```

```
TA: Yes, that's right!
```

