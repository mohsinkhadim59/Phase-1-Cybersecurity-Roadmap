# 📓 Day 3

**Focus: Bandit 7- 10** 
🔗 **Learning Links:**
- 🎮 [OverTheWire Bandit](https://overthewire.org/wargames/bandit/)
- [Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)
## Tasks
- [x] Task 7 ✅ 2025-09-01
	- [x] The command `ls -l` is used to list all the files with the details including all that of owner, group and permissions etc. which can be seen in the tip. ✅ 2025-09-01
	- [x] `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null` using this command in which user bandit7 and group bandit 6 has access contains the password. ✅ 2025-09-01

- [x] Task 8 ✅ 2025-09-03
	- [x] Using `du -b <filename>` to tell the data in the form of bytes instead of blocks/kilobytes. ✅ 2025-09-03
	- [x] Using `grep millionth data.txt` command to look for the file that has word millionth in the file and see the password in that line for the next level. ✅ 2025-09-03
- [x] Task 9 ✅ 2025-09-03
	- [x] Using the `sort <filename>` command to sort the data in alphabetical order and then using the command `uniq -u` command to extract the data that is unique. ✅ 2025-09-05
	- [x] `sort <filename> | uniq -u` ✅ 2025-09-05
- [x] Task 10 ✅ 2025-09-05
	- [x] To read the data in human readable from we use the `strings <filename>` command to extract the strings data which is readable. ✅ 2025-09-11
	- [x] Use of the `grep '==='`command to find out the password next to the line containing `equal 2 signs`. ✅ 2025-09-11

>[!tip] Important
>This shows how the `ls -l` command works while listing all the directory and its files.
>```bash
-rw-r--r--  1 user group  123 Aug 27 12:03 filename
│ │ │       │ │     │     │   │              └── File name
│ │ │       │ │     │     │   └── Date & time last modified
│ │ │       │ │     │     └── File size (in bytes)
│ │ │       │ │     └── Group owner
│ │ │       │ └── User owner
│ │ │       └── Number of hard links
│ │ └── Permissions (read/write/execute)
│ └── File type (- = file, d = directory, l = symlink, etc.)


## Findings
- Command(s): 

| Command                                                             | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           | Category |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `ls -l`                                                             | List all the files in the directory with the details including<br>permissions and last modified etc.                                                                                                                                                                                                                                                                                                                                                                                                                                  | Linux    |
| `find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null` | `find /` → start searching from the root directory `/`.<br>    <br> `-type f` → only look for **files** (not directories, links, etc).<br>    <br> `-user bandit7` → file must be owned by **user `bandit7`**.<br>    <br>`-group bandit6` → file must belong to the **group `bandit6`**.<br>    <br> `-size 33c` → file must have an exact size of **33 bytes** (`c` = bytes).<br>    <br>`2>/dev/null` → send all **error messages** (like “Permission denied”) to `/dev/null`, which discards them, so you only see valid results. | Linux    |
| `du -b <filename>`                                                  | will show you the **exact size of `data.txt` in bytes**.<br> `du` → disk usage<br> `-b` → report size in **bytes** instead of blocks/kilobytes                                                                                                                                                                                                                                                                                                                                                                                        | Linux    |
| `grep <pattern> <filename>`                                         | `grep` = **Global Regular Expression Print**<br>prints all the line containing the pattern                                                                                                                                                                                                                                                                                                                                                                                                                                            | Linux    |
| `wc -l file`                                                        | counts **lines** in the file                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          | Linux    |
| `sort <filename>`                                                   | To sort the data in the alphabetical order                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            | Linux    |
| `uniq -u`                                                           | To report or omit repeated lines                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      | Linux    |
| `strings data.txt <pipe> grep '==='`                                | To covert the data into human readable form and using the `grep` to extract the desired results                                                                                                                                                                                                                                                                                                                                                                                                                                       | Linux    |


  
## Reflections
- What I learned today:
```bash
ls -l
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
du -b <filename>
grep <pattern> <filename>
sort <filename> | uniq -u
strings <filename> | grep ===
```

- What needs review:

>[!Abstract]
> The above mentioned link in the `Piping and Redirection` link mentioned above which you have to go through.
>
> - **STDIN (0):** Standard input (data fed into the program)  
> - **STDOUT (1):** Standard output (data printed by the program, defaults to the terminal)  
> - **STDERR (2):** Standard error (for error messages, also defaults to the terminal)  
>
> ```bash
> Examples Saving to a File and Redirecting From a File
> 1. ls > output # "The greater than operator ( > ) indicates to the command line that we wish the programs output (or whatever it sends to STDOUT) to be saved in a file instead of printed to the screen"
> 2. wc -l <filename> > output # "Count the lines in the file and writes the new data in the `output` file "
> 3. ls >> output # "Using `>>` the new data is appended to the file instead of remvoving the previous data"
> 4. wc -l < <filename> # "If we use the less than operator ( < ) then we can send data the other way. We will read data from the file and feed it into the program via it's STDIN stream."
> 5. When we ran it redirecting the contents of the file into wc the file name was not printed. This is because whenever we use redirection or piping.As a result, this mechanism is often used in order to get `ancillary data` (which may not be required) to not be printed.
>  
> ```
> ```bash
> Examples Redirecting STDERR
> 1. ls -l video.mpg blah.foo 2> errors.txt # "You know what this command is doing."
> 2. 1. ls -l video.mpg blah.foo > myoutput 2>&1 # "Saving both the output STDERR and STDOUT in the filenamed myouput."
> ```
> 
> ```bash
> Examples of Piping
> 1. ls | head -3 | tail -1  # "Using the Piping to pass the ouput to the next command"
>
> ```


>[!Example]
>These are few advanced examples for the learning purposes from the `Piping and Redirection`
>```bash
>2. ls -l /etc | tail -n +2 | sort # "Starting From line 2 Onwards"
>3. ls -l / | grep "^..w" # "Starting from the start and figuring to which file the owner has permission to write"
>4. ls -l /etc | less # "`less` is a pager: it lets you scroll through text one screen at a time instead of dumping it all at once."
>5. 1. ls -l /projects/ghosttrail | tail -n +2 | sed 's/\s\s*/ /g' | cut -d ' ' -f 3 | sort | uniq -c # "Figure this command in the upcoming lessons"
>```
 
 
 
[Cheatsheet-Tree](Cheatsheet-Tree.md) 🔗
[Cheatsheet-Global](Cheatsheet-Linux.md) 🔗
[Cheatsheet-Linux](Cheatsheet-Linux.md) 🔗
