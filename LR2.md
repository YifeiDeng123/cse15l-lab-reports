# 1.Part 1
![Image](code.png)
<br>![Image](step1.png)
<br>(1) The methods public String handleRequest and public static void main are called.
<br>(2) For the method public String handleRequest the argument is URI url, and the value is String[] parameters. For the main method, the argument is String[] args and the value is int port.
<br>(3) For the class Handler, URI url changes to http://localhost:4000/add-message?s=Hello!, String str changes to 1. Hello! + "\n". For the class StringServer, int port changes to 4000.
<br>![Image](step2.png)
<br>(1)The methods public String handleRequest and public static void main are called.
<br>(2)For the method public String handleRequest the argument is URI url, and the value is String[] parameters. For the main method, the argument is String[] args and the value is int port.
<br>(3)For the class Handler, URI url changes to http://localhost:4000/add-message?s=How%20are%20you, String str changes to “1. Hello!” + "\n" + “2. How are you” +  "\n". For the class StringServer, int port changes to 4000.

