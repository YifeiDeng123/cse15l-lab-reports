# 1.cd
![Image](cd.png)
<br>(1)<br>* The working directory is in /home
<br>* The single cd with no argument does not change the directory, so there is no change or lines pop out.
<br>* There is no output, so it is not an error.
<br>(2)<br>* The working directory is in /home
<br>* The cd with argument "lecture1/messages" changes the directory to /home/lecture1/messages.
<br>* There is no error.
<br>(3)<br>* The working directory is in /home/lecture1/messages
<br>* The cd with argument "en-us.txt" is used to find the folder en-us.txt under messages.
<br>* There is an error because en-us.txt is not a folder but a file.
# 2.ls
![Image](ls.png)
<br>(1)<br>* The working directory is in /home
<br>* The single ls with no argument just lists the files or folders under the current working directory, so it prints lecture1.
<br>* There is no error.
<br>(2)<br>* The working directory is in /home
<br>* The ls with argument "lecture1" lists files or folders under the directory of /home/lecture1, so it prints "Hello.class Hello.java messages README".
<br>* There is no error.
<br>(3)<br>* The working directory is in /home
<br>* Since /lecutre1/messages/en-us.txt is not a directory, it just prints the "/lecutre1/messages/en-us.txt".
<br>* I think it is not an error, but we are not using ls to do the things it should do.

# 3.cat
![Image](cat.png)
<br>(1)<br>* The working directory is in /home
<br>* The single cat with no argument is not a complete call, so I need to type ^C to finish it.
<br>* It is not a complete call and does nothing, so there is no error.
<br>(2)<br>* The working directory is in /home
<br>* The cat with the argument "lecture1/messages" wants to print the contents of the file this path is given.
<br>* There is an error because lecture1/messages is a directory but not a file.
<br>(3)<br>* The working directory is in /home
<br>* The command cat with the argument /lecutre1/messages/en-us.txt prints the content of "en-us.txt", which is "Hellow, world!"
<br>* There is no error.
