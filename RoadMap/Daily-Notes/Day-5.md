# 📓 Day 5

**Focus:** TASK NAME

## Tasks
- [ ] Task 1
- [ ] Task 2

## Findings
- Command(s): 

| Command                    | Description                                                     | Category |
| -------------------------- | --------------------------------------------------------------- | -------- |
| `type <cmd>`               | Shows if `<cmd>` is builtin, alias, or external program         | Linux    |
| `which <cmd>`              | Shows the path to the external program (if not a builtin/alias) | Linux    |
| `command -V <cmd>`         | Similar to `type`, often more detailed                          | Linux    |
| `apropos <keyword>`        | To find commands related to specific keywords                   | Linux    |
| `ncal`                     | To show the month of the calendar with the current date         | Linux    |
| `time`                     | To get the current date and time                                | Linux    |
| `figlet -f slant <"name">` | To print the enlarged `name` in the slant font                  | Linux    |

## Reflections

- What I learned today:




- What needs review:

>[!Info]  Understand Built-in and External Commands
>Some of the commands are Built-in and then there are External commands which can be configured as per the requirements/desire of the user:
>
>```bash
>1. type cd  #we get the ouput cd is a shell builtin 
>2. type ls #ls is an alias for ls --color=tty
>```
>| Command | Type                           | Location / Source                                                           | Why it matters                                                                                            |
| ------- | ------------------------------ | --------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| `cd`    | **Shell builtin**              | Built into the shell itself (e.g., `bash`, `zsh`)                           | Needed to change directories in the current shell process. External programs couldn’t do this.            |
| `ls`    | **External program (aliased)** | Real binary: `/bin/ls` (or `/usr/bin/ls`) <br> Alias: `ls='ls --color=tty'` | `ls` runs the actual `/bin/ls` command, but your shell rewrites it with `--color=tty` for colored output. |



[Cheatsheet-Linux](Cheatsheet-Linux.md) 🔗
[Cheatsheet-SSH](Cheatsheet-SSH.md)🔗
[Cheatsheet-Global](Cheatsheet-Global.md)🔗