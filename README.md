# Linux commands that also works on bash
- Create a Dir `mkdir name_of_dir`
- Go inside the Dir `cd name of the dir`
- Come out of the Dir `cd ..` or ``cd``
- Who am I `uname -a`
- Where am I `pwd`
- Create file `touch name_of_the_file` or `nano file_name` you land inside the file
- Exit from nano `^X` then `Y` then `enter`(Mac keyboard)
- List all `ls -a` or `ls`
- To see the content of the file on terminal `cat file_name`
- Clear your screen `clear`
- Delete folder `rm -rf name_of_the_folder`
- Delete file `rm name_of_the_file`
- Delete a file or multiple files `rm file_name second_file_name`
- Copy files or group of files or directory `cp first_file second_file`
- `man` command in linux is used to display the user manual of any command that we can run on the terminal

# More linux
- To display linux processes `top`.
- To become root user `sudo` su.
- To see the history of commands `history`.
- To check the status of a process `systemctl status process_name`.
- To stop a process `systemctl stop process_name`.
- To restart a process `systemctl restart process_name`.
- To make a script you must write `#!/bin/bash` at the start of the file and use a `.sh` file type.
- To run a file type `sudo bash ./file_name.sh`.
- To change a files mode to executable `sudo chmod +x file_name.sh`.
- Once executable, run a script by making it `sudo ./provision.sh`.
- To view a snapshot of the current processes `ps`
- To kill a process `kill [process id]`
- `kill -9` Meaning the process will be killed by the kernel; this signal cannot be ignored. 9 means KILL signal that is not catchable or ignorable
- `Tail` is a command which prints the last few number of lines (10 lines by default) of a certain file, then terminates.
- `Head` command will obviously on the contrary to tail, it will print the first 10 lines of the file.
- The `sort` command arranges text lines in useful ways. This simple tool can help you quickly sort information from the command line.
- `nl`- Sometimes you may required to count number of lines in a file on Linux command line or shell scripting.
- `wc` command as described can be used to get the number of newlines, words or bytes contained in a file specified.
- The “pipe” command is readily available on UNIX/Linux platforms. This command pipes the output of the previous command to the next command. There are literally TONS of situations where this method offers serious value.Before jumping deeper, there’s something to know of. Every single program in the UNIX/Linux system has 3 built-in data streams.
  - STDIN (0) – Standard input
  - STDOUT (1) – Standard output
  - STDERR (2) – Standard error
  - When we’re going to work with “pipe” tricks, “pipe” will take the STDOUT of a command and pass it to the STDIN of the next command.

#### Wildcard Pattern Matching
`?` – matches any single character 
`*` – Matches any sequence of characters (including the empty sequence)
##### Example
```
Text = "baaabab",
Pattern = “*****ba*****ab", output : true
Pattern = "baaa?ab", output : true
Pattern = "ba*a?", output : true
Pattern = "a*ab", output : false 
```
[Reference](https://www.youtube.com/watch?v=98e_J3bexwE)
#### How to Hide Files
The period (.) at the beginning of the new filename indicates that it’s hidden:
```
mv test.txt .test.txt
```
To verify the file is now hidden, display the contents of the current directory:

```
ls –a
```
## Permissions

Linux permissions dictate 3 things you may do with a file, read, write and execute. They are referred to in Linux by a single letter each.

__r__ (read) - you may view the contents of the file.
__w__ (write) - you may change the contents of the file.
__x__ (execute) - you may execute or run the file if it is a program or script.


For every file we define 3 sets of people for whom we may specify permissions.

#### Owner

The user who owns the file. Typically the person who created the file but ownership can be changed.

#### Group

Every file belongs to a single group. Groups can have many users in it so you can give access to multiple people.

#### Others

Everyone else who is not in the group or the owner.

Three persmissions and three groups of people. That's about all there is to permissions really. Now let's see how we can view and change them.

### View Permissions

To view permissions for a file we use the long listing option for the command ls.

ls -l [path]

### Change Permissions

To change permissions on a file or directory we use a command called "chmod" It stands for change file mode bits which is a bit of a mouthfull but think of the mode bits as the permission indicators.

```
chmod [permissions] [path]
```

chmod has permission arguments that are made up of 3 components

There are two ways you can use chmod and you will see both used. One is shorter and one is more descriptive.

The privileges are summed up and depicted by one number. Therefore, the possibilities are:

- 7 – for read, write, and execute permission
- 6 – for read and write privileges
- 5 – for read and execute privileges
- 4 – for read privileges

[Reference](https://phoenixnap.com/kb/linux-file-permissions)

## Environment Variables
- To create a envi

`~/.bashrc`, `~/.profile`, `~/.bash_profile`

#### List Environment Variables
To display the value of the HOME environment variable you would run:
```
printenv HOME
```
If you run the `printenv` or `env` command without any arguments it will show a list of all environment variables

#### Setting Environment Variables
To create a new shell variable with the name `MY_VAR` and value `Linuxize` simply type:
```
MY_VAR='Linuxize'
```
You can verify that the variable is set by using either `echo $MY_VAR` of filtering the output of the set command with grep `set | grep MY_VAR`:
```
echo $MY_VAR
```
```
Output
Linuxize
```
The `export` command is used to set Environment variables.
```
export MY_NEW_VAR="My New Var"
```

#### Persistent Environment Variables
To make Environment variables persistent you need to define those variables in the bash configuration files.
- Per-user shell specific configuration files. For example, if you are using Bash, you can declare the variables in the `~/.bashrc`:
```
export PATH="$HOME/bin:$PATH"
```
To load the new environment variables into the current shell session use the `source` command:
```
source ~/.bashrc
```
## How to reverse proxy
[How to reverse proxy](https://phoenixnap.com/kb/nginx-reverse-proxy)
### What you enter in your conf file
```
server {
	listen 80;

	server_name _;

	location / {
		proxy_pass http://192.168.10.100:3000;
		proxy_http_version 1.1;
		proxy_set_header Upgrade $http_upgrade;
		proxy_set_header Connection 'upgrade';
		proxy_set_header Host $host;
		proxy_cache_bypass $http_upgrade;
	}
}
```

## Manually generating your SSH key in macOS
To generate SSH keys in macOS, follow these steps:

1. Enter the following command in the Terminal window.
 ```
 ssh-keygen -t rsa
 ```
2. Press the ENTER key to accept the default location. The ssh-keygen utility prompts you for a passphrase. 
3. Type in a passphrase. You can also hit the ENTER key to accept the default (no passphrase). However, this is not recommended.

After you confirm the passphrase, the system generates the key pair.
```
Your identification has been saved in /Users/myname/.ssh/id_rsa.
Your public key has been saved in /Users/myname/.ssh/id_rsa.pub.
The key fingerprint is:
ae:89:72:0b:85:da:5a:f4:7c:1f:c2:43:fd:c6:44:38 myname@mymac.local
The key's randomart image is:
+--[ RSA 2048]----+
|                 |
|         .       |
|        E .      |
|   .   . o       |
|  o . . S .      |
| + + o . +       |
|. + o = o +      |
| o...o * o       |
|.  oo.o .        |
+-----------------+
```
Your private key is saved to the id_rsa file in the .ssh directory and is used to verify the public key you use belongs to the same github account.

**Never share your private key with anyone!**

- go to your GitHub profile and go to Settings
- go to the SSH keys
- Click Add SSH key, enter the contents of the id_rsa.pub file
- Enter GitHub password when prompted

