# 📓 Day 7

**Focus:** TASK NAME

## Tasks
- [ ] Task 1
- [ ] Task 2

## Findings
- Command(s): 
- Notes: 

## Reflections
- What I learned today:

| Command                                                                  | Description                                                                            | Category |
| ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------- | -------- |
| `cut -d: -f1 /etc/group`                                                 | The explanation for this command is given below but in short it lists all the `groups` | Linux    |
| `result=$(echo "scale=2; (10.5 * 4.2) - (5.5 / 2) + 3^2" \| bc)`<br><br> | Using `scale` to set the decimal places<br>Using the `bc` command for calculator<br>   | Linux    |
| `echo "Result: $result"`                                                 | Using `echo` to output the results                                                     |          |
- What needs review:
> [!Info] `cut -d: -f1 /etc/group`
> ### Explanation
>
>- **`cut`** → A command that extracts sections from lines of files (kind of like slicing text by columns).
  >  
>- **`-d:`** → Sets the **delimiter** to a colon (`:`).
   > 
   > - In `/etc/group` (and also `/etc/passwd`), each line is separated into fields by colons.
   >     
   > - Example line from `/etc/group`:
   >     
   >     `sudo:x:27:bob`
   >     
   >     Here the fields are:
   >     
   >     1. `sudo` → group name
   >         
   >     2. `x` → password placeholder
   >         
   >     3. `27` → group ID (GID)
   >         
>        4. `bob` → members
   >         
>- **`-f1`** → Extract the **first field** only (before the first `:`).
>   - From the example above, `sudo:x:27:bob` → gives `sudo`.
 >       
>- **`/etc/group`** → The file containing all group definitions.



>[!tip] "Difference between `$result` vs `$( ... )`"
>```bash
>#!/bin/zsh 
># Complex calculation using bc with scale 
>result=$(echo "scale=2; (10.5 * 4.2) - (5.5 / 2) + 3^2" | bc) 
>echo "Result: $result
>```
>
>- `$result` → **variable expansion** → insert the value of the variable.
   > 
>- `$( ... )` → **command substitution** → insert the output of a command.
>
>```bash
>#!/bin/zsh 
># Script to demonstrate using variables in bc 
># Define input values
> radius=5 height=10 
> # Calculate cylinder volume (π * r² * h)
>  volume=$(echo "scale=2; 3.14159 * $radius * $radius * $height" | bc)
>   # Calculate cylinder surface area (2π * r² + 2π * r * h) 
>  surface_area=$(echo "scale=2; 2 * 3.14159 * $radius * $radius + 2 * 3.14159 * $radius * $height" | bc) 
>   # Display results 
>   echo "Cylinder properties with radius $radius and height $height:"
>   echo "Volume: $volume cubic units" echo "Surface Area: $surface_area square units"
>```

>[!Example] Making the above code simple and easy using `EOF`
>```bash
>#!/bin/zsh 
># Script to demonstrate using variables within bc
>  bc << EOF
>  scale=2 
>  radius = 5 
>  height = 10
>  pi = 3.14159 
>  # Calculate cylinder volume 
>  volume = pi * radius^2 * height 
>  print "Volume: ", volume, " cubic units\n" 
>  # Calculate cylinder surface area 
>  surface_area = 2 * pi * radius^2 + 2 * pi * radius * height 
>  print "Surface Area: ", surface_area, " square units\n"
>  EOF
>```

[Cheatsheet-Tree](Cheatsheet-Tree.md) 🔗
