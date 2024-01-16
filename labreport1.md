# CSE 15L
## Lab Report 1
1. Command `cd`

   The `cd` command is used to change the current working directory to the given path.
   
   ***

   - **using the `cd` command with no arguments**

    1. ![Image](Screenshot%202024-01-11%20130911.png)
  
    2. When the command was used the current working directory was `/home`
  
    3. When the `cd` command is used without any arguments, by default it changes the current working diectory to `/home`
  
    4. The output is not an error.

   ***
  
   - **using the `cd` command with a path to a directory as an argument**

    1. ![Image](Screenshot%202024-01-15%20174815.png)

    2. Before using the `cd` command, the working directory was `/home`. After the command, the directory changed to `/home/lecture1` and then to `/home/lecture1/messages`.
  
    3. When we give `lecture1` as an argument, the prompt changes to `[user@sahara ~lecture1/]` to show that `lecture1` is the current working directory.
  
    4. The output is not an error.
  
   ***

   - **using the `cd` command with a path to a file as an argument**
  
    1. ![Image](https://github.com/jia-aneja/cse15l-lab-reports/blob/main/Screenshot%202024-01-15%20181136.png)
  
    2. Before using the `cd` command, the working directory was `/home/lecture1`. After the command, the current working directory remains the same.
  
    3. We got the following output:
       `bash: cd: README: Not a directory`
       This is because the `cd` command only takes directories as arguments and not files.

    4. The output is an error as it demonstrates that `README` is not a directory and that the `cd` command only takes directories.
  
   ***

2. Command `ls`

   The `ls` command is used to list the files and folders in the given path.

   ***

   - **using the `ls` command with no arguments**

     1. 
     
