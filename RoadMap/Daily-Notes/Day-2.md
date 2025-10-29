# 📓 Day 2

**Focus: Bandit 3 - 6**  
🔗 **Learning Links:**
- 🎮 [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
## Tasks
- [x] Bandit 3 ✅ 2025-08-21
	- [x] Handle spaces in filename with: ✅ 2025-08-21
		 - [x] `cat -- "--spaces in this filename--"` ✅ 2025-09-01
- [x] Bandit 4 ✅ 2025-08-23
	- [x] In this task we have to list all the hidden files that are in the directory ✅ 2025-08-23
		- [x] `ls -a` was used to list all the hidden files and then using the `cat` to read that file. ✅ 2025-08-23
- [x] Bandit 5 ✅ 2025-08-23
	- [x] Used to find which one is human readable file and has password ✅ 2025-08-23
	- [x] `file ./*` tells the file types and we can see the human readable files *ASCII-Text* ✅ 2025-08-23
- [x] Bandit 6 ✅ 2025-08-23
	- [x] There are many directories all containing lot of files and you have to find the password in one of those files. ✅ 2025-08-23
	- [x] `find . -type f -size 1033c ! -executable -exec file { } \; | grep "text"` this commands first find all the files containing 1033 characters then finds non-executable files along with the use of file command to list the file type of that particular file for identification alongwith looking for the text word in that file type mentioned. ✅ 2025-09-01
	- [x] `find . -type f -size 1033c ! -executable -exec cat { } \;` where this command is reading the contents of that particular file. ✅ 2025-08-23



>[!tip] TIP OF THE DAY
>Learn To Use the commands more often and there are commands with different type of syntaxes which are to be used which are specific to purpose.
>
## Findings
- Command(s): 

| Command                                                     | Description                                                                                                     | Category |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------- | -------- |
| `cat -- "<filename>"`                                       | Stops treating anything after the `--` as a flag/option so consider it as filename                              | Linux    |
| `ls -a`                                                     | This command is used to list all the hidden files that are in the current directory                             | Linux    |
| `file./*`                                                   | To list all the human readable files                                                                            | Linux    |
| `find . -type f -size 1033c ! -executable -exec cat { } \;` | Finds all the files with 1033 characters size which are not executable and then reads the contents of that file | Linux    |


## Reflections
- What I learned today:
```bash
cat -- "--spaces in this filename"
ls -a
file ./* 
find . -type f -size 1033c ! -executable -exec cat { } \;
find . -type f -size 1033c ! -executable -exec file { } \;|grep text
```
- What needs review:
	
	>[!Important]
	These commands needs practice again and again just to get the hands on experience of using these commands plus one can jog the brain and the muscles memory to get into the experience of typing the correct flags.


[Cheatsheet-Linux](Cheatsheet-Linux.md) 🔗
[Cheatsheet-SSH](Cheatsheet-SSH.md)🔗
[Cheatsheet-Global](Cheatsheet-Global.md)🔗