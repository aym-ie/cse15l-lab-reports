# Lab Report 1

The first step in logging into the course-specific account on `ieng` would be to install VSCode. I already had VSCode on my device, but this is what it should look like when opening VSCode.

![Image](VSCode.png)

---

For remotely connecting, I first set up `git bash` in VSCode. I then opened a new terminal and set it to bash instead of powershell. In that new terminal, I then typed the command `ssh cse15lsp23bq@ieng6.ucsd.edu` into the terminal. `sp23` should be replaced by your current quarter and year, and `bq` should be replaced by the letters in *your* course specific account.

After typing this command, the terminal asks if you want to connect to the server. Type `yes` and continue. You are then prompted to type in your password for the course specific account. The terminal does not show the characters as you type it in, so just type the password and press enter. After entering my password, the following was shown. I struggled with logging in at first because I had changed my AD password rather than setting the course specific account password.

![Image](remoteconnecting.png)

---

The last step was to try some commands. The following were the commands that were used.

* `cd ~`
* `cd`
* `ls -lat`
* `ls -a`
* `ls /home/linux/ieng6/cs15lsp23/cs15lsp23ab`
* `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`
* `cat /home/linux/ieng6/cs15lwi23/public/hello.txt`


The following image displays the results from the commands.

![Image](testcommands.png)

After these commands, I used CTRL + D to logout from the remote server.
