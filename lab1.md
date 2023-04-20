# Lab Report 1

The first step in logging into the course-specific account on `ieng` would be to install VSCode. I already had VSCode on my device, but this is what it should look like when opening VSCode.

Download VSCode [here](https://code.visualstudio.com/download).

![Image](VSCode.png)

---

For remotely connecting, I first set up `git bash` in VSCode. I then opened a new terminal and set it to bash instead of powershell. In that new terminal, I then typed the command `ssh cse15lsp23br@ieng6.ucsd.edu` into the terminal. `sp23` should be replaced by your current quarter and year, and `br` should be replaced by the letters in *your* course specific account.

After typing this command, the terminal asks if you want to connect to the server. Type `yes` and continue. You are then prompted to type in your password for the course specific account. The terminal does not show the characters as you type it in, so just type the password and press enter. After entering my password, the following was shown. I struggled with logging in at first because I had changed my AD password rather than setting the course specific account password.

![Image](remoteconnecting.png)

---

The last step was to try some commands. The following were the commands that were used.

* `cd ~` : This command will change the directory to the home directory.
* `cd` : This command on it's own will not do anything, but when paired with a directory, it will change the directory to the one behind this command.
* `ls -lat` : This command will list the files in the current directory in the long format.
* `ls -a` : This command will list the hidden files in the current directory.
* `ls /home/linux/ieng6/cs15lsp23/cs15lsp23zz` : This command tries to access the directory of another student. It results in denied access since you do not have access to another student's directory.
* `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/` : This command will copy the file after the `cp` command.
* `cat /home/linux/ieng6/cs15lwi23/public/hello.txt` : This command will concatenate the files after the `cat` command and display the result, which in this case just shows the text in the hello.txt file.


The following image displays the results from the commands.

![Image](testcommands.png)

After these commands, I used CTRL + D to logout from the remote server.
