# CSE 15 L
## Lab Report 2

**PART 1**

***

Code for `ChatServer`

![Image](WhatsApp%20Image%202024-01-30%20at%2011.34.36%20AM.jpeg)

![Image](WhatsApp%20Image%202024-01-30%20at%2011.35.00%20AM.jpeg)

![Image](WhatsApp%20Image%202024-01-30%20at%2011.35.58%20AM.jpeg)

***

Using `/add-message`

**Example 1**
   
![Image](WhatsApp%20Image%202024-01-30%20at%2011.36.47%20AM.jpeg)

1. The `main` method creates a new `Handler` object which calls the `handleRequest` method. It also calls the `start` method in the `Server` class of `Server.java`

2. The `main` method takes one argument that is the port number which is an integer. The `'Handler` class implements the `URLHandler` interface which has the `handleRequest` method. This means that the `Handler` class must also implement the `handleRequest` method. The `handleRequest` method takes a URI as an argument. Lastly the `start` method of the `Server` class takes two arguments- the port number (in this case 4444) and the URLHandler object.

3. When we enter 4444 as the argument to the main method in the terminal, the server is started with 4444 as its port. If we change this number, then the port number changes as well. In this example, when we run the server with the request `/add-message s=Hello&user=jpolitz` then according to the `handleRequest` method of the `ChatServer.java` file, the else statement is executed, the request is splitted at `&` and then the two elements of the parameters are splitted at `=`. We get the message array as `["s", "Hello"]` and the user array as `["user", "jpolitz"]`. If we change the value of the message or user, then the resulting message is printed in the next line accordingly.

***

**Example 2**

![Image](WhatsApp%20Image%202024-01-30%20at%2011.37.11%20AM.jpeg)

1. In the above example, only the `handleRequest` method is called. The `start` and `main` methods are not called because the Server is already started and running at port 4444.

2. In this example, we are not executing any files, we are only updating the message shown by updating the URL using the `add-message` string. The `handleRequest` method checks if the path of the URI conatins `add-message` and then the string is split multiple times.

3. In this example, when we run the server with the request `/add-message?s=How are you&user=yash` then according to the `handleRequest` method of the `ChatServer.java` file, the else statement is executed, the request is splitted at `&` and then the two elements of the parameters are splitted at `=`. We get the message array as `["s", "How are you"]` and the user array as `["user","yash"]`. The message `yash: How are you` is printed in the next line because the previous line `jpolitz: Hello` ends with a `\n`.

***

## TASK 2

![Image](Screenshot%202024-01-30%20200948.png)

![Image](Screenshot%202024-01-30%20201000.png)

1. Absolute path to the private key is `C:\Users\jiaan/.ssh/id_rsa`.

![Image](Screenshot%202024-01-30%20140517.png)

2. Absolute path to the public key is `/home/linux/ieng6/oce/82/janeja/.ssh/id_rsa.pub`.

3. Logging into the `ieng6` account without entering the password:

![Image](Screenshot%202024-01-30%20141505.png)

Using the `mkdir` and `scp` commands I ran on the terminal when I generated the keys, I was able to log into the `ieng6` remote account without entering my password. Now any time I login, I am not asked my password, and I can log in directly.

***

## TASK 3

From the week 2 and 3 lab, I learnt how to start my own server using a port number and I wrote my own java code to add messages from the URI that show up on the server. I also learnt how to connect my laptop to a remote server and access the private and public keys.

***

