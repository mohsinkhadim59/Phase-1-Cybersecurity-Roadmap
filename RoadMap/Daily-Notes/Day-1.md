# 📓 Day 1

**Focus: Bandit 0 - 2**
🔗 **Learning Links:**  
- 🎮 [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [Advance Bash Scripting Guide-Special Characters](https://linux.die.net/abs-guide/special-chars.html) 
## Tasks
- [x] Bandit 0 ✅ 2025-08-20
	- [x] Accessing the Bandit Game Server Using SSH ✅ 2025-08-18
	- [x] `ssh <username> -p <portnumber>` ✅ 2025-08-18
		- [x] `ssh bandit0@bandit.labs.overthewire.org -p 2220` ✅ 2025-08-18
- [x] Bandit 1 ✅ 2025-08-18
	- [x] using cat command to read the password in the readme file ✅ 2025-08-18
		- [x] `ls` to list the files in the directory ✅ 2025-08-21
		- [x] `cat readme` to get the password ✅ 2025-08-21
- [x] Bandit 2 ✅ 2025-08-21
	- [x] Handling dashes in the filename using the `cat` command
		- [x] `cat ./-` to get the password ✅ 2025-08-21


## Findings
-  Commands

| Command                     | Description                                         | Category |
| --------------------------- | --------------------------------------------------- | -------- |
| `ssh <username> -p <port>`  | Connect via Secure Shell                            | SSH      |
| `ls`                        | List all the files in the current working directory | Linux    |
| `cd`                        | Change directory                                    | Linux    |
| `mktemp -d`                 | Making temporary working directory                  | Linux    |
| `cat <filename>`            | Show the contents of the file                       | Linux    |
| `cat <filename> <filename>` | Show both files one after another                   | Linux    |
| `file`                      | Identify the file type                              | Linux    |
| `du -h <file>`              | How much space files/folders use                    | Linux    |
| `cat ./-`                   | To open the dashed file                             | Linux    |


> [!tip] Handling filenames starting with `-`
> Always use `--` before the filename so Linux doesn’t treat it as a flag.


## Reflections
- What I learned today:

  ```bash
	ssh bandit0@bandit.labs.overthewire.org -p 2220
	cat readme
	cat ./-
	```
- What needs review:
		All the files are stored inside the `Bandit` directory in which i have saved in the text files using the `cat > <content>` and then we can save the line/content and then you can save the name of the file while exiting in the current working directory.

>[!Warning]
 The above mentioned link in the `Advance Bash Scripting Guide - Special Characters` link mentioned above which you have to go through.

[Cheatsheet-Linux](Cheatsheet-Linux.md) 🔗
[Cheatsheet-SSH](Cheatsheet-SSH.md)🔗
[Cheatsheet-Global](Cheatsheet-Global.md)🔗



 