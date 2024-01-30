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

Example 1
   
![Image](WhatsApp%20Image%202024-01-30%20at%2011.36.47%20AM.jpeg)

1. The `main` method creates a new `Handler` object which calls the `handleRequest` method. It also calls the `start` method
   in the `Server` class of `Server.java`

2. The `main` method takes one argument that is the port number which is an integer. The `'Handler` class implements the
   `URLHandler` interface which has the `handleRequest` method. This means that the `Handler` class must also implement the
   `handleRequest` method. The `handleRequest` method takes a URI as an argument. Lastly the `start` method of the `Server`
   class takes two arguments- the port number (in this case 4444) and the URLHandler object.

3. When we enter 4444 as the argument to the main method in the terminal, the server is started with 4444 as its port. If we change
   this number, then the port number changes as well. In this example, when we run the server with the request
   `/add-message s=Hello&user=jpolitz` then according to the `handleRequest` method of the `ChatServer.java` file, the else
   statement is executed, the request is splitted at `&` and then the two elements of the parameters are splitted at `=`.
   We get the message array as `["s", "Hello"]` and the user array as `["user", "jpolitz"]`. If we change the value of the message or
   user, then the resulting message is printed in the next line accordingly.

***

Example 2

![Image](

