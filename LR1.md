# 1.cd
![Image](cd1.png)
<br>(1)<br>* The working directory is in /home/lecture1
<br>* The single cd with no argument takes us to the home directory.
<br>* It is not an error.
![Image](cd2.png)
<br>(2)<br>* The working directory is in /home
<br>* The cd with argument "lecture1/messages" changes the directory to /home/lecture1/messages.
<br>* There is no error.
![Image](cd3.png)
<br>(3)<br>* The working directory is in /home/lecture1/messages
<br>* The cd with argument "en-us.txt" is used to find the folder en-us.txt under messages.
<br>* There is an error because en-us.txt is not a folder but a file.
# 2.ls
![Image](ls1.png)
<br>(1)<br>* The working directory is in /home
<br>* The single ls with no argument just lists the files or folders under the current working directory, so it prints lecture1.
<br>* There is no error.
![Image](ls2.png)
<br>(2)<br>* The working directory is in /home
<br>* The ls with argument "lecture1" lists files or folders under the directory of /home/lecture1, so it prints "Hello.class Hello.java messages README".
<br>* There is no error.
![Image](ls3.png)
<br>(3)<br>* The working directory is in /home/lecture1
<br>* Since messages/en-us.txt is not a directory but a file path, there is no file to list. So it just prints the "messages/en-us.txt".
<br>* I think it is not an error.

# 3.cat
![Image](cat1.png)
<br>(1)<br>* The working directory is in /home
<br>* After typing the single cat with no argument, it takes me to a new line. Then I type 123 and it prints 123. When I type "print this". it prints "print this". It seems that the cat with no argument will return the content of what you typed. Finally, I typed ^C to finish it.
<br>* It is not an error.
![Image](cat2.png)
<br>(2)<br>* The working directory is in /home
<br>* The cat with the argument "lecture1/messages" wants to print the contents of the file this path is given.
<br>* There is an error because lecture1/messages is a directory but not a file.
![Image](cat3.png)
<br>(3)<br>* The working directory is in /home
<br>* The command cat with the argument /lecutre1/messages/en-us.txt prints the content of "en-us.txt", which is "Hellow, world!"
<br>* There is no error.
