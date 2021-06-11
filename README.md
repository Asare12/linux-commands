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

#### How to Hide Files
The period (.) at the beginning of the new filename indicates that it’s hidden:
```
mv test.txt .test.txt
```
To verify the file is now hidden, display the contents of the current directory:

```
ls –a
```
