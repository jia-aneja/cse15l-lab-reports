# CSE 15L
## Lab Report 1

1. **Command `cd`**

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
  
    1. ![Image](Screenshot%202024-01-15%20181136.png)
  
    2. Before using the `cd` command, the working directory was `/home/lecture1`. After the command, the current working directory remains the same.
  
    3. We got the following output:
       `bash: cd: README: Not a directory`
       This is because the `cd` command only takes directories as arguments and not files.

    4. The output is an error as it demonstrates that `README` is not a directory and that the `cd` command only takes directories.
  
   ***

2. **Command `ls`**

   The `ls` command is used to list the files and folders in the given path.

   ***

   - **using the `ls` command with no arguments**

     1. ![Image](Screenshot%202024-01-16%20115557.png)
    
     2. When the `ls` command is run the current working directory is `/home`.
    
     3. We get the output `lecture1` in the first case because the folder in the current working directory `/home` is `lecture1`. In the second case, when the current working directory is changed to `/home/lecture1/`, we get the output `Hello.class  Hello.java  messages  README` because those are the files and the folders in the current directory. `lecture1` and `messages` are in blue and bold because folders are depicted in a different way than files.
    
     4. The output is not an error.
    
   ***

   - **using the `ls` command with a path to a directory as an argument**

     1. ![Image](Screenshot%202024-01-16%20121226.png)
    
     2. When the `ls` command is run the current working directory is `/home`.
    
     3. When we give `lecture1` as an argument with the `ls` command, it gives `Hello.class  Hello.java  messages  README` as the output because it lists all the files and folders in the `lecture1` directory.
    
     4. The output is not an error.
    
   ***

   - **using the `ls` command with a path to a file as an argument**
  
     1. ![Image](Screenshot%202024-01-16%20124401.png)
    
     2. When the `ls` command is run the current working directory is `/home`. After the command `cd lecture1` the current working directory changes to `/home/lecture1`. After the `cd messages` command the current working directory changes to `/home/lecture1/messages`.
    
     3. When we give `README` as the argument to the `ls` command, it returns the same file name i.e `README` as the output because it lists out the specific file name mentioned in the path. When we give `en-us.txt` as the argument, it returns the same file name as the output. When we give the command `ls README` when the working directory is `/home`, it throws an error, `ls: cannot access 'README': No such file or directory` because the `README` file is in the `lecture1` directory and cannot be accessed from the current working directory.
    
     4. An error is thrown when we try to access a file in a directory that is not our current directory. The error message is `ls: cannot access 'README': No such file or directory`. But if we use the correct paths and directories, the output is not an error.
    
   ***

3. **Command `cat`**

   "Concatenate"
   This command is used to print the contents of one or more files given by the paths.

   ***

   - **using the `cat` command with no arguments**

     1. ![Image](Screenshot%202024-01-16%20134056.png)
    
     2. When the `cat` command is run the current working directory is `/home`.
    
     3. When the `cat` command is run without any argument, it by default reads data from the terminal since it does not have any files to read. If we write anything in the terminal after the `cat` command, it returns the keyboard input as the output in the terminal because the program is still running. We can see that the program is still running because `[user@sahara~]$` does not show up in the subsequent lines of the terminal.
    
     4. The output is not an error.

   ***
    
   - **using the `cat` command with a path to a directory as an argument**

     1. ![Image](Screenshot%202024-01-16%20135044.png)
    
     2. When the `cat` command is run the current working directory is `/home`.
    
     3. We get the output `cat: lecture1/: Is a directory` because the `cat` command only accepts files as arguments and not directories.
    
     4. We get an error as we cannot use directories as arguments for the `cat` command. The error is `cat: lecture1/: Is a directory`.
    
   ***

   - **using the command with a path to a file as an argument**

     1. 
     
