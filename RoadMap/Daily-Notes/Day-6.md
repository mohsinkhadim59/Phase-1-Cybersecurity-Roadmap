# 📓 Day 6

**Focus:** TASK NAME

## Tasks
- [ ] Task 1
- [ ] Task 2

## Findings
- Command(s): 
- Notes: 

## Reflections
- What I learned today:

| Command                                     | Description                                                                                                                                                                                             | Category |
| ------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------- |
| `whoami`                                    | To display the name of the current user                                                                                                                                                                 | Linux    |
| `sudo adduser jack`                         | Create a new user named "jack"<br>Create a new group named "jack" (the primary group)<br>Add the user "jack" to the "jack" group as its primary group<br>Create a home directory for jack at /home/jack | Linux    |
| `id <username>`                             | Show the `uid` , `gid` and `secondary groups`                                                                                                                                                           | Linux    |
| `cat /etc/group <pipe> sort`                | `cat` command displays file contents<br>`/etc/group` is where group information is stored<br>`sort` sorts the output alphabetically                                                                     | Linux    |
| `cat /etc/group \| grep -E "labex"`         | Show only groups related to labex                                                                                                                                                                       | Linux    |
| `sudo groupadd developers`                  | Creating a new group named developers                                                                                                                                                                   | Linux    |
| `sudo usermod -aG developers jack`          | adding jack to the new group created<br>The `usermod` command modifies user accounts. The `-aG` option adds the user to a supplementary group.                                                          | Linux    |
| `groups jack`                               | Checking the groups the `user` mentioned is currently a part of                                                                                                                                         | Linux    |
| `sudo usermod -aG sudo jack`                | command uses `usermod` to modify the user account. The `-aG` option means "append to group", so it adds jack to the #sudo_group without removing him from other groups.                                 | Linux    |
| `sudo groups jack`                          | Listing all the groups of which username is a part of                                                                                                                                                   | Linux    |
| `sudo chown jack:jack /home/labex/testfile` | Changing the ownership of file both the user and the group at the same time                                                                                                                             | Linux    |
| `ls /home`                                  | This directory can be listed to see all the `users`                                                                                                                                                     | Linux    |

>[!tip] 
> - `su` stands for Superuser Do which runs the command as a superuser (or root user)
> - There are two types of a groups-- `the primary and the secondary groups`
> 	- User is part of a primary group but can be part of multiple secondary groups.
> 	- When you create a new user with `adduser`, it automatically creates a primary group for that user with the same name as the username. This is called a User Private Group (UPG) scheme.
> 	
- What needs review:

> [!Info] Understanding and Manipulating File Permissions and Ownership
> In this section we will learn about the use of the `chmod` command to change the permissions of the file to its respective `User , Group and Others`.
> ```bash
> 1. 7 (owner): Read (4) + Write (2) + Execute (1) = 7
>2. 5 (group): Read (4) + Execute (1) = 5
>3. 0 (others): No permissions
>```
>This permission set means:
>
>- The owner (jack) can read, write, and execute the file
>- Members of the jack group can read and execute the file
>- Others have no permissions on the file
> 


[Cheatsheet-Tree](Cheatsheet-Tree.md) 🔗
