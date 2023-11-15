## Step 4: Log into ieng6
![Image](login.png)
<br> To login ieng6, I typed the command "ssh cs15lsp23si@ieng6.ucsd.edu" and then pressed the key <enter> to execute the command. Since I have set up the keys for easy access, I don't need to enter my password.
## Step 5: Clone your fork of the repository from your Github account
![Image](clone.png)
<br> To clone the repository, I first copied the SSH link from my GitHub. Next, I typed the command "git clone git@github.com:YifeiDeng123/lab7.git" and then pressed the key <return> to execute the command. 
## Step 6: Run the tests, demonstrating that they fail
![Image](FailTest.png)
<br> To run the test, I first typed "ls" to check whether lab7 has been cloned successfully. Then I typed "cd lab7" to go into lab7's directory. Next, I typed "ls" to check the files in the folder of lab7. Finally, I typed the command "bash test.sh" and then pressed the key <enter> to execute the command. 
## Step 7: Edit the code file to fix the failing test
![Image](open.png)
<br> To edit the code file, I first open ListExamples.java in vim by typing the command "vim ListExamples.java" and pressing the <enter> key.
![Image](vim.png)
<br> Now I am in the normal mode of vim. First, I need to navigate to "index1" in the final loop in merge method in order to change it to "index2". To do so, I press "<ctrl> + d" three times to get to the end of the code. 
![Image](vim2.png)
<br> Then I pressed up arrow key 6 times to get to the beginning of the line where I wanted to make a change. Next, I press "f" + "1" to  jump to just before the next occurrence using 1. Then I pressed the right arrow key to get to the place that I wanted to edit. 
![Image](vim3.png)
<br> After that, I pressed "i" to get into the insert mode. Next, I pressed <backspace> and typed "2" to change "index1" to "index2".
![Image](exit.png)
<br> Finally, I pressed the key <esc> to return to the normal mode and typed ":wq" to save and exit the vim.
