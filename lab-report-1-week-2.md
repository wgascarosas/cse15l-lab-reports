# Part 1: Installing VScode

The first step is to instal VScode from this website: 
[Install VScode](https://code.visualstudio.com/)

![image](Installing_vscode.png)

As seen in the picture above, download the VScode that corresponds to your computer operating system. (macOS for Macs and Windows x64 for PCs)

**NOTE: VScode does not support chromebooks or tablets**

# Part 2: Remotely Connecting

Once VScode is downloaded we can access the terminal in it.

———————————————————————————————————————————

**NOTE: Windows users need to install a program called OpenSSH**
- Install here: [Open SSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse)
- then look for you specific cse15l account here: [ucsd account](https://sdacs.ucsd.edu/~icc/index.php)

———————————————————————————————————————————

You can press control + \` or command + ` to open a terminal in VScode (alternatively you can go to Terminal and then New Terminal).
To access the remote ieng6 server you type in the following command 

`$ ssh cs15lwi22zz@ieng6.ucsd.edu`

with the `zz` being replaced by your specific account letters.

You will get asked to put in your password and once you do your terminal should look like this… 

![image](remotely_connecting.png)

Now you are good to go and start commanding!

**to log out at any time you can press control + D or type in exit**

# Part 3: Trying Some Commands

Try to run some commands now that you are connected to the remote servers.
Here is a list of commands to try… 

- `cd`
- `ls -a`
- `pwd`
- `mkdir`
- `cat`
- `cp`

When `ls -a` is typed as a command this lists all the files in the directory in which you are currently in 

![image](commands.png)

# Part 4: Moving Files with scp

A useful command is `scp` which is used to copy a file or multiple files from your computer to a remote one. 

To move a file from your computer to a remote one we would use the following syntax… 

`scp  ____name of file to copy____   ____cs15lwi22zz@ieng6.ucsd.edu:~/____`

with the `zz` replaced by your specific account letters.

You will be asked to enter your password and one entered the file should be copied to the remote account. 
(To verify that the file is in the remote account log into the remote server using ssh and type in ls command, you should see the file there; in the picture below the file copied is named WhereAmI.java)

![image](using_scp.png)

# Part 5: Setting an SSH Key

We can use ssh keys to avoid retyping your password every time we connect to the remote ieng6 server. To do this run the command `ssh-keygen` on your (client) computer. Then you will be prompted with the following … 

- `# on client (your computer)`
- `$ ssh-keygen`
- `Generating public/private rsa key pair.`
- `Enter file in which to save the key (/Users/user/.ssh/id_rsa): /Users/user/.ssh/id_rsa`
- `Enter passphrase (empty for no passphrase): `
- `Enter same passphrase again:` 
- `Your identification has been saved in /Users/user/.ssh/id_rsa.`
- `Your public key has been saved in /Users/user/.ssh/id_rsa.pub.`
- `The key fingerprint is:`
- `SHA256:jZaZH6fI8E2I1D35hnvGeBePQ4ELOf2Ge+G0XknoXp0 user@User-Mac-mini.local`
- `The key's randomart image is:`
- `+---[RSA 3072]----+`
- `|                 |`
- `|       . . + .   |`
- `|      . . B o .  |`
- `|     . . B * +.. |`
- `|      o S = *.B. |`
- `|       = = O.*.*+|`
- `|        + * *.BE+|`
- `|           +.+.o |`
- `|             ..  |`
- `+----[SHA256]-----+`

![image](ssh-key.png)

Now log in to your remote ieng6 server account using

`ssh cs15lwi22zz@ieng6.ucsd.edu` 

with `zz` replaced by your account specific letters.
Once logged in run command `mkdir .ssh` then log out.
Now on your computer terminal run the command....

`scp /Users/user/.ssh/id_rsa.pub cs15lwi22@ieng6.ucsd.edu:~/.ssh/authorized_keys`

(You use your username and the path you saw in the command above)

Now you can ssh or scp from your computer to the remote one without using a password.

# Part 6: Optimizing Remote Running

To run commands on the remote server from your computer you can write the command in quotes. For example typing… 

`ssh cs15lwi22@ieng6.ucsd.edu "ls -lat”`

will display all the files in the home directory of the remote server and the time they were crated. 

![image](optimization.png)

Notice how we are still in our own terminal and not the remote server’s.

You can also type in multiple commands using a semicolon like the example below… 

`ssh cs15lwi22@ieng6.ucsd.edu "ls -lat; cd ~; pwd; ls”`
